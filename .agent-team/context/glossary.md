# Glossary

- Active piece: The currently controllable tetromino not yet locked into the board.
- Local Coding Model: The privately configured local model that is the only implementation model for this experiment.
- Board: The authoritative 10-column by 20-visible-row logical playfield.
- Coding: Any application source, scene/resource, test, harness, configuration, script, CI, or export-setting change.
- FallingBlock: The project and game name.
- Hard drop: Move the active piece to its lowest valid row and lock immediately.
- Handoff: A persisted role-to-role record under `docs/handoffs/`.
- Lock: Transfer the active piece's occupied cells into authoritative board state.
- Soft drop: Manually move the active piece down one row.
- Terra: GPT-5.6 Terra, used for design, architecture, work management, review, documentation, and release judgment.
- Tetromino: A game piece consisting of four connected cells.
- Seven-bag: A randomization method that emits each of the seven tetromino identities once per shuffled bag.
- Wall adjustment: Limited deterministic horizontal correction attempted during rotation near a boundary.
