# chironbuilds2's October Contributions

A summary of security contributions by chironbuilds2 in October 2026:

* Reported an rPC session-count leak vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-7h97-fwqj-6qpm`.
* The report showed that the rPC server leaked the per-client session count on handshake failure, permanently locking out a peer and growing the session map unbounded.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2764`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#80`.
