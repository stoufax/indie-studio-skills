---
name: studio-startup
description: Start or configure the game studio in a repository - inspect the real project, fill verified facts in studio/PROJECT.md, run parallel audience discovery and feasibility inspection, and stop with a concrete prototype plan. Use when the user says to start the studio, set up a new game project, or when PROJECT.md is still marked UNCONFIGURED.
metadata:
  pack: codex-game-studio
  version: "1.0"
---

# Studio startup

The lead (main conversation) turns an unconfigured repository into a planned first milestone. It ends with a plan, not a built game.

## Inputs

- `AGENTS.md`, `studio/PROJECT.md`, `studio/BACKLOG.md`, `studio/DECISIONS.md`.
- The actual repository: engine files, existing instructions, working-tree changes, available tools.

## Steps

1. **Inspect before asking.** Identify the engine and exact version, target devices, input method, and existing build/test commands. Run only commands that already exist in the project. Record each verified command, environment, and outcome in the Verified environment table of `PROJECT.md`. Use `NOT AVAILABLE` where a check cannot run.
2. **Record tool access.** Fill the Tool access table with what this session can actually use. Unverified stays unverified.
3. **Ask only blocking questions.** If the concept, engine, platform, or a commercial commitment is undecided and blocks progress, ask the user one focused question. Continue independent inspection meanwhile. Label provisional assumptions in `PROJECT.md`.
4. **Delegate in parallel** using the `task-contract` skill for each brief:
   - `marketing_research` runs `audience-discovery`, output `studio/research/discovery.md`.
   - `systems_engineer` inspects technical feasibility, output `studio/work/feasibility.md`.
   Give them separate output paths and no shared writable files.
5. **Design the smallest experiment.** After both report, have `game_designer` use `core-loop-spec` on their findings, output `studio/work/core-loop.md`.
6. **Update lead documents.** Update `BACKLOG.md` statuses with real outputs and add a `DECISIONS.md` entry for the proposed first milestone, with evidence IDs, uncertainty, and review trigger.
7. **Stop** with a prototype plan: player outcome, uncertain assumption under test, acceptance criteria, task owners, and what needs the user's decision.

## Rules

- Never more than three specialist threads open at once; close finished ones.
- Do not build an unchosen game, install an engine without a real need, or invent engine commands.
- No outreach, publication, purchases, or spend.
