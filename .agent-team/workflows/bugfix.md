# Bugfix Workflow

## Purpose

Reproduce, fix, and verify a defect with minimal unrelated change.

## Sequence

1. Work Manager moves the defect to In Progress.
2. Product Owner confirms expected behavior and severity.
3. QA Engineer reproduces the defect when possible and records evidence.
4. Game Designer clarifies expected player behavior when needed.
5. Architect acts only for complex or cross-boundary fixes.
6. Godot Engineer implements the smallest safe fix and regression coverage.
7. QA Engineer verifies reproduction no longer succeeds and checks the regression area.
8. Work Manager accepts, merges, closes, and records results.

## Gates

Stop for behavior changes beyond restoring approved behavior, new dependencies, broad refactors, or platform/release changes.
