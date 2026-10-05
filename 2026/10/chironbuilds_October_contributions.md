# chironbuilds's October Contributions

A summary of security contributions by chironbuilds in October 2026:

* Reported a template compile fee under-pricing vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-jmhq-55mw-648w`.
* The report showed that the fee for publishing a template under-priced the validators' compile cost. It included measurements, a proof of concept, and a suggested fix.
* Testing was performed locally only; no shared network was touched.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2747`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#49`.
* Reported a dry-run input lookup amplification vulnerability in the `tari-ootle` indexer, submitted through GitHub Security Advisories and tracked in `GHSA-p677-8mxp-3mfj`.
* The report showed that one unauthenticated dry-run request to the indexer could fan out into unbounded per-input validator-node lookups. It included a root-cause analysis and a suggested fix.
* Testing was performed locally only; no shared network was touched.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2744`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#47`.
* Reported a `submit_transaction` RPC decode amplification vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-6mvf-8pp4-3c5j`.
* The report showed that the RPC handler decoded a transaction in full before enforcing its size cap, letting a 6 MiB frame amplify into roughly 640 MiB of heap allocation.
* Testing was performed locally only; no shared network was touched.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2761`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#56`.
