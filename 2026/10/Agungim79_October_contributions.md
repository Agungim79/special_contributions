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
