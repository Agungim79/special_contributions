# Agungim79's October Contributions

A summary of security contributions by Agungim79 in October 2026:

* Reported an unauthenticated consensus request-handling vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-86p9-mv74-3g3p`.
* The report showed that the consensus request handlers served `MissingTransactionsRequest` and `ForeignProposalRequest` messages from non-committee peers, letting an unauthenticated peer stall the consensus dispatch loop and exhaust the inbound message queue.
* Provided root-cause analysis, runnable proofs of concept at the worker, transport and committee level, and measured impact.
* Testing was performed locally only; no shared network was touched.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2738`. The contribution is tracked in `tari-project/special_contributions#38`.
