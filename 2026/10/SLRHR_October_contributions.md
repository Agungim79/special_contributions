# Security contribution for issue #64

Security report for GHSA-q7qg-fgqp-p96v.

The report identified that public liquidity pools allowed arbitrary LP token minting and reserve theft.

The fix was implemented separately by @sdbondi in tari-project/tari-ootle#2759. This file records the contribution for the retro bounty; no code changes are required.


# Security contribution for issue #109

Security report for the direct stealth UTXO burn authorization-bypass issue acknowledged in tari-project/special_contributions#109.

The report identified that the StealthUtxoBurn path could bypass the expected resource authorization hook.

The fix was implemented separately. This file records the contribution for the retro bounty; no code changes are required.
