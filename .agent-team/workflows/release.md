# Release Workflow

## Purpose

Validate and package an approved Linux desktop release candidate.

## Sequence

1. Work Manager identifies included merged issues and candidate commit.
2. QA Engineer confirms complete automated, headless, and manual-play evidence.
3. Godot Engineer creates or fixes implementation-side export configuration only when a ticket authorizes it.
4. Release Manager runs documented checks, verifies the Linux artifact launches on the target Linux workstation, and prepares release notes.
5. Product Owner confirms the release matches approved MVP scope.
6. Release Manager issues a go/no-go recommendation.
7. the project owner approves any public publication.

## Completion

Required checks pass, documentation matches actual commands, the candidate is reproducible from a clean checkout, rollback target is recorded, and unresolved risk is explicit.
