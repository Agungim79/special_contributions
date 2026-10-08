# chironbuilds3's October Contributions

A summary of security contributions by chironbuilds3 in October 2026:

* Reported a default access-rule vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-h8rm-c49w-w5rx`.
* The report showed that the default access rules of `ResourceBuilder::non_fungible()` left `update_non_fungible_data` at `AccessRule::AllowAll`, letting any caller permanently overwrite NFT data.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2786`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#75`.
