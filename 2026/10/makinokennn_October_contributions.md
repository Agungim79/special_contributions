# makinokennn's October Contributions

A summary of security contributions by makinokennn in October 2026:

* Reported an epoch_manager stale-committee vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-mq5v-4h4g-49w6`.
* The report showed that the Equal arm of `activate_epoch` performed hash-only correction on reorg rescan, leaving committee assignments stale after a deep L1 reorg that changed the validator set at an epoch boundary. It included a root-cause analysis, an executable proof of concept, and a suggested fix.
* Testing was performed locally only; no shared network was touched.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2810`. Technical details remain in the advisory. The contribution is tracked in `tari-project/special_contributions#91`.
