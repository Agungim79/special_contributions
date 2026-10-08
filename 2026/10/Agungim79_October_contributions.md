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
