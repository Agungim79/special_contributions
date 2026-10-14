# chironbuilds2's October Contributions

A summary of security contributions by chironbuilds2 in October 2026:

* Reported an rPC session-count leak vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-7h97-fwqj-6qpm`.
* The report showed that the rPC server leaked the per-client session count on handshake failure, permanently locking out a peer and growing the session map unbounded.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2764`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#80`.
* Reported a state-sync vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-pq7v-fwv7-jxq8`.
* The report showed that state sync durably committed unverified peer-supplied consensus state before the root check, with no rollback, causing a permanent self-DoS and an integrity violation.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2765`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#78`.
* Reported a substate exclusion proof vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-2xjh-wg9w-g5hc`.
* The report showed that a substate exclusion proof was not bound to the substate's shard, so a serving validator could prove false absence ("destroyed") for any substate.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2762`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#82`.
