---
name: studio-resume
description: Resume game studio work in a new session from the repository's durable records - PROJECT.md, BACKLOG.md, DECISIONS.md, evidence ledger, and working tree - then continue the next ready task within existing authorization. Use when the user says resume, continue, pick up where we left off, or opens a new session on a configured studio project.
metadata:
  pack: studio-crew
  version: "1.0"
---

# Studio resume

Conversation memory is not durable; the repository is. Rebuild context from it before acting.

## Steps

1. Read `studio/PROJECT.md`, `studio/BACKLOG.md`, the latest entries in `studio/DECISIONS.md`, and the evidence IDs those entries cite in `studio/research/EVIDENCE.md`.
2. Inspect the working tree. Note uncommitted changes and any reports under `studio/work/` or `studio/research/` newer than the last decision. Never reset or discard changes you did not make.
3. Summarize for the user, briefly:
   - the active milestone and its acceptance criteria;
   - what is verified, with evidence, versus claimed or not run;
   - unresolved assumptions and open user decisions.
4. Pick the next `ready` backlog task that the existing authorization covers. If the next step is a material change to audience, core loop, platform, or business model, stop and ask instead.
5. Delegate independent tasks with the `task-contract` skill; handle trivial ones directly.

## Rules

- Do not recreate completed work.
- An experiment without recorded results has no results. Do not infer them.
- Stop at the current milestone; do not loop autonomously.
