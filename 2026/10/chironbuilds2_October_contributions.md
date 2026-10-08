# chironbuilds2's October Contributions

A summary of security contributions by chironbuilds2 in October 2026:

* Reported a state-sync vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-pq7v-fwv7-jxq8`.
* The report showed that state sync durably committed unverified peer-supplied consensus state before the root check, with no rollback, causing a permanent self-DoS and an integrity violation.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2765`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#78`.
