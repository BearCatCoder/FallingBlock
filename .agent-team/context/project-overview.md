# Project Overview

## Project

- Name: FallingBlock
- Repository: this repository
- Purpose: A compact falling-block puzzle and an experiment in split-model AI software delivery.
- Primary user: A desktop player using keyboard controls.
- Work tracking: GitHub issues and the GitHub Project board.

## Goals

- Deliver the approved MVP in `docs/GAME_DESIGN.md`.
- Keep authoritative rules deterministic and testable.
- Produce a playable Linux desktop export for Local Coding Model.
- Demonstrate that GPT-5.6 Terra can design/manage/review while Local Coding Model authors all implementation.

## Non-goals

- Online services, accounts, multiplayer, monetization, mobile, web export, external art, audio, controller input, persistent high scores, or full competitive rotation compatibility.
- Adding mechanics excluded by the game design.
- Using cloud coding models for implementation.

## Constraints

- Engine: Godot 4.7 Classic.
- Language: GDScript unless an approved design decision says otherwise.
- Primary runtime and export target: Linux desktop on the target Linux workstation.
- Development interface: OpenCode.
- Database/backend: none.
- One implementation issue normally active at a time.

## Source of truth

1. Approved GitHub issue
2. `docs/GAME_DESIGN.md`
3. `docs/AI_WORKFLOW.md`
4. `.agent-team/context/`
5. Latest role handoff
