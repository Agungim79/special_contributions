# chironbuilds4's October Contributions

A summary of security contributions by chironbuilds4 in October 2026:

* Reported a transaction finalization vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-734p-gq7p-3pwq`.
* The report showed that a transaction could finalize AllAccept in its output shard group while the input shard group never accepted it, because the dead `all_objects_accepted()` check was never replaced.
* Coordinated the finding through private disclosure; the fix was applied by the Tari team in `tari-ootle#2771`. Technical details remain in the advisory until it is published. The contribution is tracked in `tari-project/special_contributions#79`.
