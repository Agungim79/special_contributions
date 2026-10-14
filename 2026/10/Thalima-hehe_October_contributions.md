# Thalima-hehe's October Contributions

A summary of security contributions by Thalima-hehe in October 2026:

* Reported a validation bypass in `tari-ootle` where foreign proposals attached to leader blocks skip validation, enabling forged cross-shard state, submitted through GitHub Security Advisories and tracked in `GHSA-ffmc-66pq-4cgx`.
* The report showed that when a leader proposes a block, attached foreign proposals from other shard groups are never run through `check_foreign_proposal`, so a malicious leader can attach forged proposals with fabricated state and validators will execute cross-shard transactions against the false data without any check.
* Provided root-cause analysis and a runnable in-repo proof of concept. Testing was performed locally only; no shared network was touched.
* Coordinated the finding through private disclosure; the fix was implemented by the Tari team in `tari-ootle#2827`. The contribution is tracked in `tari-project/special_contributions#104`.
