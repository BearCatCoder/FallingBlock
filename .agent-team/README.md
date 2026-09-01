# FallingBlock Agent Team

This is a project-specific adaptation of a reusable agentic development-team pattern, following the vendored approach proven in a larger project.

## What was retained

- One role acts at a time.
- Every role reads project context before acting.
- Explicit handoffs preserve decisions between model turns.
- Scope and architecture changes require approval.
- QA verifies written acceptance criteria.
- Work discovered outside scope becomes separately managed work.

## What was changed for FallingBlock

- Enterprise roles that have no MVP responsibility were removed.
- A Game Designer role was added.
- Frontend and backend implementation roles were replaced by one Godot Engineer.
- Work Manager explicitly owns the GitHub issue/Project lifecycle.
- Model ownership is a hard boundary: Terra performs design and management; Local Coding Model performs all coding.
- Pull-request evidence records the experiment's implementation and review cycles.

## Layout

- `agents/`: role definitions and boundaries
- `workflows/`: issue, bug, design-change, and release sequences
- `templates/`: handoff, implementation, QA, and decision records
- `context/`: FallingBlock-specific project knowledge and constraints
