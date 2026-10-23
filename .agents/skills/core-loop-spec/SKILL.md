---
name: core-loop-spec
description: Turn an audience hypothesis into the smallest playable, testable game design spec - controls, rules, state transitions, feedback, failure and recovery, progression, tunable values, edge cases, a cut list, and acceptance criteria. Use when designing a core loop, mechanic, level, or progression change, or when a pivot needs a prototype that distinguishes competing explanations.
metadata:
  pack: codex-game-studio
  version: "1.0"
---

# Core loop spec

Write a design that engineers can build and QA can check, scoped to what the next playtest needs to learn.

## Inputs

`studio/PROJECT.md`, the relevant audience report and evidence IDs, and the current playable build or code, if any. Read them before proposing anything.

## Spec sections

Write to the assigned path (default `studio/work/core-loop.md`). Include only the sections the task needs:

1. **Player promise** - one sentence, tied to an evidence ID or labeled hypothesis.
2. **Why this serves the audience** - one line per mechanic.
3. **Controls** for the target device and input, including touch-target and readability notes on mobile.
4. **Rules and state transitions** - start, play, fail, recover, restart, pause.
5. **Feedback** - what the player sees and hears for each important event.
6. **Progression and session length.**
7. **Tunable values** - name, starting value, range. Mark all as untested hypotheses.
8. **Edge cases.**
9. **Interfaces needed** from engineering, for the lead to agree before parallel work.
10. **Acceptance criteria** - observable, one per behavior.
11. **Cut list** - what is deliberately left out of this version.
12. **Design risks** - what could make this fail with players.

## Rules

- Start with the smallest playable version; reject feature accumulation.
- Do not claim a mechanic is fun; only playtests show that. Keep design review separate from observed player feedback.
- Consider accessibility and readability on the target device.
- Do not change the target audience or rewrite engine architecture.
- For a pivot, design the cheapest prototype whose result would favor one explanation over another.
