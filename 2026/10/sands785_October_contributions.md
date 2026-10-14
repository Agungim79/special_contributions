## sands785's October Contributions

A summary of security contributions by sands785 in October 2026:

## [Bug Hunt] Unauthenticated cross-shard QC replay forces consensus sync loop, halting committee liveness (GHSA-p6cp-739m-2hrv)

- **Severity:** Moderate (published, filed as High)
- **Package:** tari_consensus <= 0.43.0
- **CWE:** CWE-345
- **Summary:** Unauthenticated cross-shard QC replay via `probe_future_epoch_qc` forces the committee into a consensus sync loop, halting liveness. Foreign QCs are verified against the foreign committee without binding to the local shard group.
- **Fix:** tari-project/tari-ootle#2836
- **Retro bounty issue:** tari-project/special_contributions#107
