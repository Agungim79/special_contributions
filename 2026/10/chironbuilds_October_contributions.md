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
* Reported an `nfts.transfer` fee-payment and signing scope vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-jg8h-hw4h-5fmv`.
* The report showed that `nfts.transfer` paid the transaction fee from, and signed with, an account the caller had no scope on.
* Testing was performed locally only; no shared network was touched.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2785`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#71`.
* Reported a `claim_burn` vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-j9v4-vq99-f484`.
* The report showed that `claim_burn` minted the claimed UTXO to the seal signer's key, locking a relayer-sealed claim's funds behind the relayer.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2800`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#87`.
* Reported a transaction-finalization vulnerability in the `tari-ootle` wallet, submitted through GitHub Security Advisories and tracked in `GHSA-p5x5-x636-37pg`.
* The report showed that the wallet applied an unverified finalization diff taken from a single committee member's first answer, letting one malicious validator mark real inputs spent, record phantom change, or release the locks of committed transactions.
* Testing was performed locally only; no shared network was touched.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2838`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#108`.
