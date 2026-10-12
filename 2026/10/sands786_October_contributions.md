## sands786's October Contributions

A summary of security contributions by sands786 in October 2026:

- Reported a forged cross-shard foreign proposal pledge vulnerability in `tari-ootle` through GitHub Security Advisories (`GHSA-m298-6jj3-fg7c`).

- The report demonstrated that foreign proposal pledge values were not bound to quorum certificates, enabling unbacked cross-shard asset minting.

- Provided a passing proof-of-concept test, root cause analysis, and fix suggestion to the Tari team.

- These contributions are tracked by `tari-project/special_contributions#83`.

- Reported a wallet daemon denial-of-service vulnerability in `tari-ootle` through GitHub Security Advisories (`GHSA-g234-qrqg-35ch`).

- The report demonstrated that a single 2 KB manifest with deeply nested parentheses causes the manifest parser to overflow its stack, aborting the entire walletd daemon process.

- Provided a passing proof-of-concept test, root cause analysis, and fix suggestion to the Tari team.

- These contributions are tracked by `tari-project/special_contributions#92`.

## [Bug Hunt] Unmetered template return value decoding bypasses compute budget (GHSA-wjvw-6j6r-x7q6)

- **Severity:** Moderate (published)
- **Package:** tari_engine <= 0.43.0
- **CWE:** CWE-400
- **Summary:** Template return values decoded via `IndexedValue::from_raw` outside the compute meter, allowing up to 128 KiB per return value to bypass the compute budget entirely.
- **Fix:** tari-project/tari-ootle#2858
- **Retro bounty issue:** tari-project/special_contributions#122
