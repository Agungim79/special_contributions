# Security Reports - October 2026

## Report 1 - GHSA-24f6-ghpp-4h32

Reported by SriCharan Pedhiti (@cherry1809)

Stealth resource actions bypass the resource auth hook in tari-ootle.
StealthUtxoBurn has no spend authorization or freeze check.
The fix was applied by the Tari team in tari-ootle#2787.

## Report 2 - GHSA-xq6m-fw4q-529x

Reported by SriCharan Pedhiti (@cherry1809)

tari-cli exfiltrates wallet bearer API key to attacker URL in project
tari.config.toml — fires before any confirmation prompt.
The fix was applied by the Tari team in tari-cli#220.

Technical details remain in the advisory until it is published.
