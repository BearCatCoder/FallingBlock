# Issue Delivery Workflow

## Purpose

Deliver one approved GitHub issue with strict Terra/Local Coding Model separation.

## Required inputs

- Active GitHub issue
- Latest repository state
- Project context
- Prior handoff, if any

## Sequence

1. **Work Manager / Terra**
   - Confirm dependencies are complete.
   - Move the issue to In Progress.
   - Record the active issue and next role.
2. **Product Owner / Terra**
   - Confirm outcome, scope, non-scope, and measurable acceptance criteria.
   - Skip a new artifact when the issue is already unambiguous; record that determination.
3. **Game Designer / Terra, when player behavior or presentation is affected**
   - Clarify player-facing rules and edge cases.
4. **Architect / Terra**
   - Define the smallest compliant technical approach and affected boundaries.
5. **Godot Engineer / Local Coding Model**
   - Create an issue branch.
   - Implement only approved scope.
   - Run validation and open a pull request.
   - Write an implementation handoff.
6. **Work Manager / Terra**
   - Move the issue to Review.
7. **QA Engineer / Terra**
   - Inspect and run existing checks.
   - Produce a QA report.
8. **Correction loop**
   - On failure, Terra reports observable defects.
   - Local Coding Model makes all code/test/config fixes and updates evidence.
   - QA reruns affected validation.
9. **Work Manager / Terra**
   - Confirm acceptance, merge, close, and move to Done.
   - Record metrics and create follow-up issues.

## Gates

Stop for the project owner's approval when work requires an unplanned gameplay change, new dependency/plugin, major architecture change, platform expansion, or public release.

## Completion

All acceptance criteria pass, required evidence is present, no unresolved blocker remains, and model-boundary violations are recorded.
