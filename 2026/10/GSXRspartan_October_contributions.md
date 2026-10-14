# GSXRspartan's October Contributions

A summary of security contributions by GSXRspartan in October 2026:

* Reported a zero-value proof authorization bypass in `tari-ootle` through GitHub Security Advisories (`GHSA-pp4v-v773-9qxg`).
* The report demonstrated that a zero-value fungible proof, or an empty NFT-ID-set proof, could satisfy `resource(X)` access rules when the caller held none of the authorization resource.
* Provided engine regression tests with passing controls, a review of affected authorization surfaces, a suggested fix, and a closed-loop Esmeralda reproduction using only tester-owned dummy assets.

* Reported a stablecoin admin/deployer authority vulnerability through GitHub Security Advisories (`GHSA-4g4m-xgcp-pv55`).
* The report demonstrated that stablecoin admin/deployer authority could enable permissionless minting and unrecoverable privileged access.

* Reported an unauthenticated remote validator process-abort vulnerability in `tari-ootle` through GitHub Security Advisories (`GHSA-6hvx-j552-fffj`).
* The report demonstrated that an unauthenticated peer could trigger an integer overflow through the `sync_state` `until_epoch` field, causing the validator process to abort.
* The vulnerability was reproduced with a deterministic regression test against the affected Ootle source and was subsequently fixed separately by the Tari team in `tari-project/tari-ootle#2776`.

* All vulnerabilities were responsibly disclosed through GitHub Security Advisories, with reproduction evidence and technical analysis provided to the Tari team.
* These contributions are tracked by `tari-project/special_contributions#40`, `tari-project/special_contributions#51`, and `tari-project/special_contributions#61`.

* Reported a Tari Ootle validator availability vulnerability through GitHub Security Advisories (`GHSA-v8m9-4g8c-j2jf`).
* The report demonstrated that a committee member could remotely abort a validator through a `NodeHeight` overflow in `LeaderSkipSet`.
* Provided deterministic regression evidence showing the overflow reaches the release-build abort behavior under the affected conditions.
* The vulnerability was responsibly disclosed and subsequently fixed separately by the Tari team in `tari-project/tari-ootle#2825`.
* This contribution is tracked by `tari-project/special_contributions#100`.
