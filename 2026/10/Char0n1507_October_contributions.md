# Security Reports - October 2026

## Report 1 - GHSA-mc36-c3gm-3cj4

Reported by (@Char0n1507)

Malicious indexer crashes tari_walletd via SubstateDiff id/value 
mismatch with no authentication required (CP-2). The fix was applied 
by the Tari team in tari-ootle#2813.

## Report 2 - GHSA-9795-9pp8-phgh

Reported by (@Char0n1507)

Consensus message decode expands 24-48x beyond wire-byte accounting,
leading to remote unauthenticated memory exhaustion (OOM) of validator
nodes in tari-ootle. The fix was applied by the Tari team in 
tari-ootle#2887.

Technical details remain in the advisory until it is published.
