# Redi Sinaga's October Contributions

A summary of security contributions by redisinaga in October 2026:

- Reported a wASM metering ceiling bypass in `tari-ootle` via nested cross-template calls, submitted by email to the Tari security team.
- The report showed that `MAX_WASM_POINTS_PER_TRANSACTION` is applied only when a WASM call starts, and nothing lowers a running call's meter afterwards. A call that nests another template call and keeps running therefore spends from the meter it was handed, while the nested call spends from its own, so the frames add up instead of sharing one budget.
- Measured on a local engine: one unprivileged transaction recorded 2,247,088,311 WASM points (8.99x the 250,000,000 cap) and 4,269,168,449 points including the native charge, exceeding the reserve `max_block_validation_execution_points` leaves over `max_block_execution_points`. A leader packing two such transactions produces a block over the validation budget every validator enforces, which the code treats as a no-vote.
- Provided root-cause analysis and a runnable proof of concept. Testing was performed locally only; no shared network was touched.
- Coordinated the finding through private disclosure; the fix was implemented by the Tari team in `tari-project/tari-ootle#2817`. The contribution is tracked in `tari-project/special_contributions#135`.
