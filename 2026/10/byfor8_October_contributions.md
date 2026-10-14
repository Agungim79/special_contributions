# byfor8's October Contributions

A summary of security contributions by byfor8 in October 2026:

- Reported a host log amplification vulnerability in `tari-ootle`, submitted through GitHub Security Advisories as `GHSA-jwq8-9jwc-g52p`.
- The report showed that the `emit_log` host call writes the full guest message to the host log before the 32 KiB receipt cap is applied, letting a template multiply host log I/O on the consensus path.
- The fix was implemented separately by the Tari team in `tari-project/tari-ootle#2882`.
- Reported a wallet lock deadline rewrite vulnerability in `tari-ootle`, submitted through GitHub Security Advisories as `GHSA-vx64-fqq8-9prm`.
- The report showed that a `transaction_requests:create` scoped caller can run `locks_set_timeout` on any existing lock id without an ownership check, and the deadline write commits before approval, so a third party can extend a victim's pending request lock indefinitely.
- The fix is being implemented separately by the Tari team (in progress per tari-project/special_contributions#181).
