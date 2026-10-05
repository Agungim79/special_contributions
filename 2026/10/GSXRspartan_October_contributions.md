# GSXRspartan's October Contributions

A summary of security contributions by GSXRspartan in October 2026:

* Reported a zero-value proof authorization bypass in `tari-ootle` through GitHub Security Advisories (`GHSA-pp4v-v773-9qxg`).
* The report demonstrated that a zero-value fungible proof, or an empty NFT-ID-set proof, could satisfy `resource(X)` access rules when the caller held none of the authorization resource.
* Provided engine regression tests with passing controls, a review of affected authorization surfaces, a suggested fix, and a closed-loop Esmeralda reproduction using only tester-owned dummy assets.
* Reported a stablecoin admin/deployer authority vulnerability through GitHub Security Advisories (`GHSA-4g4m-xgcp-pv55`).
* The report demonstrated that stablecoin admin/deployer authority could enable permissionless minting and unrecoverable privileged access.
* Both vulnerabilities were responsibly disclosed and subsequently fixed separately by the Tari team.
* These contributions are tracked by `tari-project/special_contributions#40` and `tari-project/special_contributions#51`.
