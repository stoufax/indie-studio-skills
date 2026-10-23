---
name: build-verification
description: Independently verify an integrated game build against its acceptance criteria - run available checks, reproduce defects, exercise restart, pause, repeated sessions, and save/load, and measure performance with full test context. Use for QA of a milestone or fix, when reproducing a reported bug, or when profiling frame time and memory before optimization.
metadata:
  pack: studio-crew
  version: "1.0"
---

# Build verification

Check what the build actually does, independent of what the implementer claims.

## Steps

1. Read the acceptance criteria and identify the exact integrated build or commit under test.
2. Run the build and tests recorded in `studio/PROJECT.md`. Record exact commands and outcomes.
3. Exercise in priority order: crashes, data loss, broken gameplay, input problems, unreadable feedback, progression blockers, performance regressions.
4. Cover start, restart, pause and resume, repeated sessions, boundary conditions, and save/load where relevant.
5. Write the report at the assigned path (default `studio/work/qa-<milestone>.md`):
   - per criterion: `pass`, `fail`, or `not run`, with evidence;
   - defects prioritized by severity;
   - milestone blockers.

## Defect format

Severity, file or symbol if known, build identifier and environment, reproduction steps, expected versus actual, and evidence. Keep observed bugs separate from suspected risks. Skip style-only findings unless they affect behavior or maintenance.

## Performance evidence

Record device, OS, engine and build mode, scenario, warm-up, duration, entity and effect counts, frame-time distribution where available, memory, and the baseline compared against. Profile before recommending structural optimization. Never extrapolate a desktop result to a guaranteed mobile result.

## Rules

- Do not edit product code; you may write the assigned report and tests. Send defects to the lead for assignment.
- Static inspection is not a playtest. Do not claim screenshots or benchmarks that were not captured.
- Mark unavailable checks `not run` with the next step needed.
- After fixes, rerun the affected checks yourself.
- Feel and appeal need human playtests.
