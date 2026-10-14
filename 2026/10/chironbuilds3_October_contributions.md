# chironbuilds3's October Contributions

A summary of security contributions by chironbuilds3 in October 2026:

* Reported a manifest parser panic vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-256m-v6v9-82mp`.
* The report showed that a `blob!("...")` manifest with an invalid identifier string panicked the parser, and that walletd's global panic hook then killed the whole daemon.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2766`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#57`.
* Reported an indexer sync-version overflow vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-pjx9-6f6w-r678`.
* The report showed that a peer-claimed `synced_to_version = u64::MAX` overflow-panicked the indexer's sync worker and that the poisoned value was persisted, so the crash recurred on every restart.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2767`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#63`.
* Reported a default access-rule vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-h8rm-c49w-w5rx`.
* The report showed that the default access rules of `ResourceBuilder::non_fungible()` left `update_non_fungible_data` at `AccessRule::AllowAll`, letting any caller permanently overwrite NFT data.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2786`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#75`.
