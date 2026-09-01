# FallingBlock Game Design

## Product statement

FallingBlock is a compact, responsive falling-block puzzle for desktop. The player arranges descending pieces to complete horizontal lines, prevent the stack from reaching the top of the playfield, and pursue a higher score as gravity accelerates.

The first release is intentionally small. Its second purpose is to test whether GPT-5.6 Terra can manage design and delivery while Local Coding Model performs all implementation work.

## Target

- Engine: Godot 4.7 Classic
- Primary platform: Linux desktop
- Presentation: native Godot 2D
- Input: keyboard
- Playfield: 10 columns by 20 visible rows
- Orientation: landscape window with centered board and adjacent HUD
- External services: none

## MVP gameplay

The MVP includes:

- All seven standard four-cell piece shapes
- A deterministic seven-piece bag randomizer
- One active piece and a visible next-piece preview
- Horizontal movement
- Clockwise rotation
- Soft drop and hard drop
- Gravity that accelerates as the player advances
- Piece locking
- Completed-line removal
- Score, level, and cleared-line counters
- Pause, restart, and game-over states
- A title/instruction state before play begins

## Rules

### Spawning

A new piece appears near the horizontal center at the top of the board. If it cannot occupy its spawn position, play ends immediately.

### Movement and collision

A requested movement succeeds only when every occupied cell remains inside the playable bounds and avoids locked cells. Failed movements must not change board state.

### Rotation

The MVP supports clockwise rotation. Rotation must be deterministic and must not overlap locked cells or leave the playfield. Limited wall adjustment is allowed so pieces can rotate next to a side wall, but advanced competitive rotation behavior is not an MVP requirement.

### Gravity and locking

Gravity advances the active piece by one row at a level-dependent interval. When downward movement is no longer possible, a short, consistent lock delay gives the player a final chance to move or rotate before the piece becomes part of the board. Hard drop locks immediately.

### Line clearing

After a piece locks, every completely occupied row is removed in one resolution step. Rows above cleared lines move downward, and empty rows enter from the top.

### Progression and scoring

- Single line: 100 × current level
- Two lines: 300 × current level
- Three lines: 500 × current level
- Four lines: 800 × current level
- Soft drop: 1 point per manually descended cell
- Hard drop: 2 points per descended cell
- Starting level: 1
- Level increases after every 10 total cleared lines
- Gravity becomes faster at each new level and remains playable rather than reaching a zero-length interval

## Game states

- Ready: title, objective, and controls are visible
- Playing: gravity and player actions affect the board
- Paused: gameplay simulation and scoring stop
- Game Over: final score is visible and the player can restart

State transitions must be explicit and testable. Restarting creates a clean session with no retained board cells, score, lines, level, queue position, or timers.

## Presentation

The board must be visually distinct from its surroundings. Each piece shape has a stable color. Locked cells and the active piece use the same shape colors. The HUD shows next piece, score, level, cleared lines, controls, and current state.

Presentation should be clear at the target window size without requiring external artwork. Animation may improve feedback but must never become the authoritative source of game state.

## Architecture constraints

- Core rules and authoritative game state remain separate from rendering and input presentation.
- Random piece generation can be given a known seed for deterministic tests.
- Board coordinates and display coordinates are separate concepts.
- UI nodes display state but do not own game rules.
- Input requests actions through the game controller rather than editing board state directly.
- Pausing and restarting cannot leave stale timers or deferred actions active.
- The implementation should favor small, cohesive Godot scripts and scenes over a single monolithic game script.

## Quality requirements

- Core rule behavior is covered by automated tests that run without manual play.
- No normal player input can create overlapping pieces or cells outside the board.
- A new game can be played repeatedly without reopening the application.
- There are no uncaught runtime errors during a complete play session.
- The repository documents how to open, test, run, and export the project.

## Explicitly out of scope

- Hold-piece mechanic
- Counterclockwise rotation
- Full competitive rotation-system compatibility
- Ghost piece
- Sound or music
- Controller or touch input
- Online leaderboard or accounts
- Multiplayer
- Saved high scores
- Mobile or web export
- Custom artwork
- Mod support
