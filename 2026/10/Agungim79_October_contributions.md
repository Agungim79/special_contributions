# Agungim79's October Contributions

A summary of security contributions by Agungim79 in October 2026:

* Reported an unauthenticated consensus request-handling vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-86p9-mv74-3g3p`.
* The report showed that the consensus request handlers served `MissingTransactionsRequest` and `ForeignProposalRequest` messages from non-committee peers, letting an unauthenticated peer stall the consensus dispatch loop and exhaust the inbound message queue.
* Provided root-cause analysis, runnable proofs of concept at the worker, transport and committee level, and measured impact.
* Testing was performed locally only; no shared network was touched.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2738`. The contribution is tracked in `tari-project/special_contributions#38`.
* Reported an unauthenticated denial-of-service in the `tari-ootle` indexer's event pagination, submitted through GitHub Security Advisories and tracked in `GHSA-7xqr-7m59-v97v`.
* Identified that the `offset` parameter on `/transactions/events` is unbounded while every sibling paging parameter is capped, so a 16-connection unauthenticated loop makes SQLite walk the whole events table per request and starve the shared connection pool; the load testing behind the numbers was local, and the six single spaced requests sent to the public Esmeralda indexer were disclosed in full.
* The fix was implemented by the Tari team in `tari-ootle#2742` and `tari-ootle#2740`. The contribution is tracked in `tari-project/special_contributions#46`.
* Reported unmetered dry-run template compilation on the indexer's dry-run endpoint, submitted through GitHub Security Advisories and tracked in `GHSA-h5pq-gqp9-rp39`.
* The fix was implemented by the Tari team in `tari-ootle#2744` and `tari-ootle#2745`. The contribution is tracked in `tari-project/special_contributions#48`.
* Reported a flaw in `tari-ootle` walletd's `confidential.create_transfer_proof`, submitted through GitHub Security Advisories.
* The report showed that the change output built by the handler omits `reveal_amount`, so the balance equation the engine verifies is off by exactly that amount and every reveal-based withdraw proof fails balance verification.
* Provided root-cause analysis, a runnable in-repo proof of concept with zero-reveal and corrected-change controls, and measured impact. Testing was performed locally only; no shared network was touched.
* Coordinated the finding through private disclosure; the fix will be implemented by the Tari team. The contribution is tracked in `tari-project/special_contributions#90`.
* Reported an unauthenticated resource-amplification defect in the `tari-ootle` indexer's REST API, submitted through GitHub Security Advisories and tracked in `GHSA-vx64-74jw-67vv`.
* The report showed that a single unauthenticated `GET /epoch-checkpoints?limit=100` returns 4,031,080 bytes and costs the origin ~0.57 s of work for a ~70-byte request line (~5.7 x 10^4 amplification), while nothing in the pipeline bounds per-request bytes or work: no response-size cap, `cache-control: no-store` with no edge absorption, and `from_epoch` varying lets a client regenerate a full-size page at a rate it chooses.
* Measured read-only on both public indexers at v0.43.0 (commit 392d805); no load testing and no shared network was touched.
* The fix was implemented by the Tari team in `tari-ootle#2823` (per-IP `epoch_checkpoints_rate` limiter for the route, page cap lowered from 100 to 20, and limits on the remaining public read routes). The contribution is tracked in `tari-project/special_contributions#101`.
* Reported an unauthenticated pre-handshake head-of-line blocking defect in `tari-ootle`'s RPC server, submitted through GitHub Security Advisories and tracked in `GHSA-6qvq-r3x2-92vg`.
* The report showed that `PeerRpcServer::serve()` awaits `handle_protocol_notification` inline inside its `tokio::select!` loop, so a peer that opens a substream on `/tari/validator/1.0.0` and sends no bytes parks the single admission task in `perform_server_handshake()` for the full 15 s timeout; each further silent substream adds another serialized 15 s, and the `self.tasks.next()` arm that reaps completed sessions is starved while it waits. Already-established sessions were unaffected.
* Measured in-tree against a local duplex socket (3 runs, all 4 tests passing): honest admission + first request 0.43-0.62 ms, one silent substream 14.70 s, two silent substreams 29.40 s, and 255-355 us round-trip on an established session during an active stall. No authentication, no completed handshake, no funds and a single libp2p connection were required; testing was local only and no Tari-owned host was contacted.
* The fix was implemented by the Tari team in `tari-ootle#2856` (handshake moved into the spawned session task, refusals written off the loop, default handshake timeout reduced from 15 s to 5 s). The contribution is tracked in `tari-project/special_contributions#124`.
* Reported a flaw in the `tari-ootle` indexer's substate value-proof verification, submitted through GitHub Security Advisories and tracked in `GHSA-h2q8-m8f7-xvv7`.
* The report showed that verification pins a quorum-signed shard-group state merkle root (the anchor) and checks the validator's inclusion/exclusion proof against it, but nothing binds the anchor to a recent block: a validator answers a read with a commit proof for any earlier committed block and the indexer adopts that block's epoch and root without comparing it to the tip, so a proof of absence taken at a root from before the substate existed verifies as `Down` while the substate is `Up` at the current root.
* Provided root-cause analysis and runnable in-tree proofs against the production verifier and the production indexer anchor path, with measured impact. Testing was performed locally only; no Tari-owned host or live validator was contacted.
* The fix was implemented by the Tari team in `tari-ootle#2885`. The contribution is tracked in `tari-project/special_contributions#155`.

* Reported a defect in `tari-ootle`'s confidential withdraw fee charging, submitted through GitHub Security Advisories and tracked in `GHSA-659x-fc98-87wp`.
* The report showed that a withdraw whose balance proof fails charges nothing for the verification it triggers: pricing applies only on success, so repeating the withdraw and forcing verification to run and fail every attempt burns consensus work the price list values at 64 x `PER_SCHNORR_VERIFY` = 70,400,000 native points for zero charge — the proof cryptography itself ran each time (the rejection reason is the invalid balance proof, not a skipped check).
* Provided root-cause analysis, an in-tree end-to-end proof at the template level with revealed-proof controls, and measured impact: 64 rejected attempts cost ~678 ms of real verification against a 14-16 ms control while the charged native points stayed at 377,692 in every run.
* The fix was implemented by the Tari team in `tari-ootle#2925`. The contribution is tracked in `tari-project/special_contributions#183`.
* Reported a flaw in `tari-ootle`'s gossip validation chain, submitted through private disclosure on 2026-10-09.
* The report showed that the node's ingress chain runs the dry-run check while the gossip chain the same message travels through does not, so a transaction that validators must reject as a sender fault is still accepted and re-gossiped by honest relays; gossipsub charges those rejects to the forwarding peer, and enough of them in one second push the honest relay's score under the greylist threshold, cutting it off.
* Provided root-cause analysis, a local multi-peer harness reproducing the greylisting from validation rejects alone, a chain-divergence proof of concept, and measured impact. Testing was performed locally only; no shared network was touched.
* The fix was implemented by the Tari team in `tari-ootle#2924`. The contribution is tracked in `tari-project/special_contributions#182`.

* Reported a host-abort defect in `tari-ootle`'s SDK intent validation, submitted through private disclosure on 2026-10-05.
* The report showed that a workspace label carrying an offset suffix is accepted by the SDK's label check but resolves through a second lookup that requires the bare name, so the builder panics; in the prebuilt release binaries the project ships to native hosts the panic aborts the process, and the caller never receives the error envelope the header promises.
* Provided root-cause analysis across both lookups, a runnable end-to-end proof against the shipped release profile with a differential control, and measured impact (exit 134, 3/3). Testing was performed locally only; no shared network was touched.
* The fix was implemented by the Tari team in `tari-ootle#2931`. The contribution is tracked in `tari-project/special_contributions#191`.

