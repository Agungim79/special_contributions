# metzee32's October Contributions

A summary of security contributions by metzee32 in October 2026:

* Reported an unmetered covenant balance-proof verification vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-g2pw-wx69-2mx8`.
* The report showed that covenant balance-proof verification in stealth transfers was not metered, so a transaction within every published limit could force minutes of validator CPU while paying for milliseconds, enabling a per-transaction consensus denial-of-service.
* Provided a call-graph analysis, a cost model, a proof-of-concept test suite, and a suggested fix.
* Reported a stealth-transfer value-inflation vulnerability in `tari-ootle`, submitted through GitHub Security Advisories and tracked in `GHSA-x485-wpxp-m89h`.
* The report showed that a stealth transfer could inflate value within a single transaction. Provided root-cause analysis, an executable proof of concept, and a suggested fix.
* Testing was performed locally only; no shared network was touched.
* Coordinated the findings through private disclosure; the fixes were applied by the Tari team in `tari-ootle#2739` and `tari-ootle#2576`. Technical details remain in the advisories. The contributions are tracked in `tari-project/special_contributions#42` and `tari-project/special_contributions#41`.
