# AI Development Workflow

## Purpose

This project tests a hard separation between design/work management and implementation.

## Model boundary

### GPT-5.6 Terra owns

- Product and gameplay design
- Architecture constraints
- Scope decisions
- GitHub issue creation and prioritization
- Acceptance criteria
- Project-board state
- Review of diffs, test evidence, and observed behavior
- Merge/readiness decisions
- Documentation under `docs/` and non-implementation project communication

Terra may inspect source code and test output. Terra must not author implementation, provide a replacement patch, or make line-level code corrections.

### Local Coding Model owns

- GDScript
- Godot scenes and resources
- `project.godot`
- Input mappings
- Test code and test infrastructure
- Import/export settings
- Build or automation scripts
- CI configuration
- Every implementation fix, refactor, and generated application file

For this experiment, all of the above counts as coding even when a file is primarily declarative.

## Delivery loop

1. Terra selects one ready GitHub issue and moves it to In Progress.
2. Terra supplies the issue, dependencies, constraints, and acceptance criteria to the Local Coding Model coding agent.
3. Local Coding Model creates an issue branch, implements only that scope, runs relevant validation, and opens a pull request.
4. Local Coding Model reports files changed, tests executed, results, limitations, and any newly discovered work.
5. Terra reviews the diff and evidence against the issue rather than rewriting the implementation.
6. If acceptance criteria are unmet, Terra describes observable defects or violated constraints.
7. Local Coding Model makes all corrective code changes and reruns validation.
8. Terra approves and merges when the issue is complete, closes the issue, and moves it to Done.
9. Work discovered outside the active issue becomes a separate GitHub issue.

## Board states

- Todo: defined and ready but not started
- In Progress: the current implementation ticket
- Review: pull request open and awaiting Terra review
- Done: accepted and merged
- Blocked: cannot proceed without a dependency or human decision

Only one implementation issue should normally be In Progress. This keeps the local model's context bounded and makes experimental results attributable.

## Ticket requirements

Every implementation ticket must contain:

- User-visible or architectural outcome
- Explicit in-scope work
- Explicit exclusions when scope could expand
- Acceptance criteria
- Required test or validation evidence
- Known dependencies

Local Coding Model should not silently broaden a ticket. Newly discovered work is reported for Terra to triage.

## Pull-request requirements

Each pull request must:

- Link its issue
- Contain only that issue's implementation
- Summarize the approach without pasting large code sections
- List automated and manual validation performed
- Call out deviations, uncertainty, and follow-up work
- Avoid unrelated cleanup

## Experiment record

For each ticket, record in the pull request:

- Number of Local Coding Model implementation attempts
- Number of Terra review cycles
- Automated test/build failures encountered
- Human implementation guidance, if any
- Model-boundary violations, if any
- Work that had to be re-scoped

The experiment succeeds when the completed game meets the design and the history clearly demonstrates that Terra did not author its code.
