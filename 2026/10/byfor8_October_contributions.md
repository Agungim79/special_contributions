# byfor8's October Contributions

A summary of security contributions by byfor8 in October 2026:

- Reported a host log amplification vulnerability in `tari-ootle`, submitted through GitHub Security Advisories as `GHSA-jwq8-9jwc-g52p`.
- The report showed that the `emit_log` host call writes the full guest message to the host log before the 32 KiB receipt cap is applied, letting a template multiply host log I/O on the consensus path.
- The fix was implemented separately by the Tari team in `tari-project/tari-ootle#2882`.
