# Agungim79's September Contributions

A summary of security contributions by Agungim79 in September 2026:

* Reported an algorithmic-complexity denial-of-service in the `minotari_node` mempool-sync responder, tracked through `GHSA-w6gq-cv3j-hrm6`.
* Identified that the responder in `base_layer/core/src/mempool/sync_protocol/mod.rs` performs a linear scan of the received inventory for every pooled transaction — O(mempool × items) — and that `inventory.items.len()` is bounded only by the 3 MiB frame, so a single peer-supplied frame can carry 92,521 items.
* Provided a reproducible in-repo PoC driving the real responder over a `MemorySocket`, with measured cost: one 3 MiB inventory against a 10,000-transaction mempool costs the node ~3.0 s of CPU (~12 s at the 40,000-transaction pool cap).
* The finding was confirmed by the maintainers against `development` at `2a6170a` and rated Low (CWE-407); the agreed remediation replaces both linear scans with hash-map lookups and caps `inventory.items.len()` at `initial_sync_max_transactions`.
* Coordinated the finding through private disclosure.
