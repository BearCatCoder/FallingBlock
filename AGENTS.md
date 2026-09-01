# FallingBlock — OpenCode Agent Guide

This repository uses a project-specific agent team under `.agent-team/`. Read this file before acting.

## Non-negotiable experiment boundary

- **GPT-5.6 Terra** owns work management, product decisions, game design, architecture, QA judgment, documentation, and release decisions.
- **Local Coding Model** owns every implementation change.
- Never substitute another model for either side without the project owner's explicit approval.
- If the active OpenCode agent is not bound to the model required by its role, stop and report the routing problem.
- One role acts at a time and writes a handoff before the next role begins.

## Public repository privacy

This repository is public. Never commit or publish:

- Personal names, usernames, email addresses, account identifiers, or authentication details
- Workstation names, network names, hostnames, IP addresses, or local service endpoints
- Local filesystem paths or model-storage paths
- Credentials, tokens, keys, cookies, or secrets
- Private provider configuration or exact local provider/model identifiers
- Machine-specific hardware, software, or environment details not required by the application

Use generic role names such as `project owner`, `Local Coding Model`, and `target Linux workstation`. Keep private model bindings and machine-specific OpenCode configuration outside the repository.

Implementation includes GDScript, Godot scenes and resources, `project.godot`, input maps, tests, test harnesses, import/export settings, CI, build scripts, and implementation fixes. Terra may inspect these files and run existing checks, but must not create, edit, patch, or dictate line-level replacements for them.

Terra may edit requirements, architecture records, issue text, review reports, handoffs, and other non-implementation Markdown.

## Required startup reading

Every session reads:

1. `.agent-team/context/project-overview.md`
2. `.agent-team/context/architecture.md`
3. `.agent-team/context/coding-standards.md`
4. `.agent-team/context/testing-standards.md`
5. `.agent-team/context/release.md`
6. `.agent-team/context/glossary.md`
7. The active GitHub issue and latest handoff

## Roles

- Work Manager — Terra
- Product Owner — Terra
- Game Designer — Terra
- Architect — Terra
- Godot Engineer — Local Coding Model
- QA Engineer — Terra
- Release Manager — Terra

Role definitions live in `.agent-team/agents/`.

## Default issue workflow

Use `.agent-team/workflows/issue-delivery.md`.

1. Work Manager selects one ready issue and moves it to In Progress.
2. Product Owner confirms scope and measurable acceptance criteria.
3. Game Designer reviews gameplay or presentation behavior when relevant.
4. Architect produces the smallest actionable technical approach.
5. Godot Engineer implements and validates only the approved issue.
6. QA Engineer verifies acceptance criteria without fixing defects.
7. Failed verification returns to the Godot Engineer.
8. Work Manager accepts and merges the pull request, closes the issue, and moves it to Done.
9. Release Manager acts only when a release candidate is being produced.

Save handoffs under `docs/handoffs/` using `.agent-team/templates/handoff.md`.

## Work-management rules

- Normally only one implementation issue is In Progress.
- The numeric prefix in each issue title defines delivery order; GitHub issue numbers may differ.
- Create a separate issue for newly discovered out-of-scope work.
- Move blocked work to Blocked and record the exact dependency or decision needed.
- The Godot Engineer may create branches, commits, and pull requests but does not redefine scope or acceptance.
- Terra may review and merge code but never authors a corrective patch.
