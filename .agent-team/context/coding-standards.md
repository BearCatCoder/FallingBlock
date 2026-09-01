# Coding Standards

## Ownership

Only the Godot Engineer running on the target Linux workstation may create or edit implementation.

## General

- Keep each issue change small and reviewable.
- Prefer explicit, readable rule logic over clever abstraction.
- Avoid unrelated formatting, refactors, or generated-file churn.
- Do not add mechanics absent from the approved issue.
- Do not add plugins or dependencies without approval.

## Godot and GDScript

- Target Godot 4.7 Classic.
- Use GDScript unless an approved decision changes the language.
- Use static typing where it improves correctness and clarity.
- Follow Godot naming conventions: snake_case functions/variables, PascalCase named classes, and UPPER_SNAKE_CASE constants.
- Keep authoritative rules independent of rendering details.
- UI nodes display or request state changes; they do not own game rules.
- Prefer signals or narrow controller interfaces over broad cross-tree mutation.
- Keep board-space calculations integer-based and deterministic.
- Treat scene/resource files as implementation subject to the same scope and review rules as scripts.

## Error handling

- Reject invalid state transitions without partially mutating state.
- Fail clearly on missing required nodes/resources or invalid configuration.
- Do not suppress parser warnings or test failures merely to obtain a green run.
- Record any engine limitation or work-around in the implementation handoff.

## Repository discipline

- One issue per branch and pull request.
- No unrelated cleanup.
- Never commit Godot editor cache/import artifacts, local credentials, or generated exports unless specifically approved.
- Update run/test instructions when commands actually change.
