# Testing Standards

## Strategy

- Unit-test deterministic piece, bag, board, movement, rotation, scoring, and state-transition rules.
- Use controller-level tests for gravity ticks, locking, spawn/game-over, pause, and restart.
- Use headless Godot validation for project loading and automated suites.
- Use focused manual play only for presentation, input feel, and end-to-end behavior that automation cannot establish.
- The test harness is selected and documented by Issue 01; adding a third-party plugin requires approval.

## Required evidence per implementation issue

- Focused automated checks for changed behavior.
- Existing affected regression checks.
- Headless project load or equivalent parser validation.
- Manual steps when visual or input behavior changes.
- Exact command/process and exit/result in the implementation handoff.

## Quality rules

- Tests assert observable behavior, not private implementation structure.
- Deterministic tests control random seeds and time/ticks.
- Rejected moves and transitions verify state remains unchanged.
- Fixes add regression coverage when practical.
- No skipped or flaky result is reported as passing.
- A pre-existing failure is documented with evidence and a separate issue; it is not silently ignored.

## Final MVP validation

Verify spawning, movement, rotation, soft/hard drop, gravity, locking, line clearing, score, levels, next preview, pause, game over, restart, repeated sessions, and Linux export launch.
