# Architecture Context

## Overview

FallingBlock is a native Godot 2D desktop game. Authoritative gameplay state is separate from rendering, UI, and raw input so core rules can be exercised deterministically without manual play.

## Logical components

- Piece definitions: identities, occupied cells, rotations, and display metadata.
- Piece source: deterministic seedable seven-bag queue.
- Board state: 10×20 logical occupancy, validation, locking, and row removal.
- Active piece: current identity, orientation, and board position.
- Game controller: state transitions, gravity, locking, spawn sequence, score, level, and reset coordination.
- Input adapter: converts configured Godot input actions into controller requests.
- Board presentation: draws active and locked cells from authoritative state.
- HUD: displays next piece, score, level, lines, controls, and current state.
- Tests: validate rule components and controller behavior without relying on rendered pixels.

Names above describe responsibilities, not mandatory class or file names.

## Data flow

Player input or a gravity tick requests an action from the controller. The controller validates through active-piece and board rules. Successful state changes update authoritative state, after which presentation reads or receives the new state. Rendering never decides whether a move, rotation, lock, clear, score, or game-over transition is legal.

## Constraints

- Board coordinates are distinct from display coordinates.
- Failed operations leave authoritative state unchanged.
- Randomness must support a known seed.
- Timers and deferred actions cannot leak across pause, game over, or restart.
- UI and animation are not authoritative.
- Prefer small cohesive responsibilities over one monolithic game script.
- New plugins or runtime dependencies require approval.

## Risks

- Spawn and rotation behavior near boundaries.
- Multiple-line compaction order.
- Lock-delay resets permitting infinite play.
- Stale timers affecting a restarted session.
- Rule logic becoming coupled to the scene tree and difficult to test.
