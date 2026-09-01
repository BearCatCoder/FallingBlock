# Release Context

## Target

A local Linux desktop build exported with Godot 4.7 Classic and launched on the target Linux workstation.

## Environments

- Development: Godot editor and headless checks on the target Linux workstation.
- Release candidate: local Linux export from a clean accepted commit.
- Public distribution: not part of the MVP and requires the project owner's approval.

## Readiness

- All MVP issues accepted and merged.
- Automated suite passes from a clean checkout.
- Headless project validation has no parser or load errors.
- Manual end-to-end checklist passes.
- Run, test, and export instructions match actual commands.
- Model-boundary and experiment metrics are summarized.

## Rollback

Because there is no service deployment or persistent data, rollback means discarding the candidate artifact and returning to the last accepted tag or commit.

## Approval gates

- New platform or packaging target
- New runtime dependency or plugin
- Public release or distribution
- Waiving a failed required check
