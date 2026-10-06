# Security Report - GHSA-24f6-ghpp-4h32

Reported by SriCharan Pedhiti (@cherry1809)

Stealth resource actions bypass the resource auth hook in tari-ootle.
StealthUtxoBurn has no spend authorization or freeze check.
The fix was applied by the Tari team in tari-ootle#2787.

Technical details remain in the advisory until it is published.
