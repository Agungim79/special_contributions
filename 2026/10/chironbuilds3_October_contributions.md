# chironbuilds3's October Contributions

A summary of security contributions by chironbuilds3 in October 2026:

* Reported an indexer sync-version overflow vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-pjx9-6f6w-r678`.
* The report showed that a peer-claimed `synced_to_version = u64::MAX` overflow-panicked the indexer's sync worker and that the poisoned value was persisted, so the crash recurred on every restart.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2767`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#63`.
