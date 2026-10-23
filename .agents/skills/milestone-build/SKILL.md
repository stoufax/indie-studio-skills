---
name: milestone-build
description: Implement an approved playable game milestone end to end - define acceptance criteria and file ownership, delegate gameplay, systems, and art work, integrate, have qa_reviewer verify, fix and re-verify, then report what needs human playtesting. Use when the user approves a prototype plan or says build the next milestone.
metadata:
  pack: studio-crew
  version: "1.0"
---

# Milestone build

The lead runs one approved milestone from contracts to verified integration, then stops.

## Preconditions

- An approved milestone exists in `studio/DECISIONS.md` or the user's request. If not, stop and run `studio-startup` or ask.
- Build and test commands are recorded in `studio/PROJECT.md`, or are explicitly `NOT AVAILABLE`.

## Steps

1. **Define done.** Write the milestone's observable acceptance criteria and its player outcome.
2. **Split work.** Write one `task-contract` per independent piece: `gameplay_engineer` (rules, movement, enemies), `systems_engineer` (save, menus, settings), `technical_artist` (readable visuals, effects). Agree interfaces before parallel work; serialize any task touching a shared file.
3. **Delegate** at most three at once. Prefer placeholders and the smallest playable step over infrastructure.
4. **Integrate.** Inspect each handoff's actual changes, merge them, and run the project's build and tests yourself.
5. **Verify independently.** Delegate to `qa_reviewer` with the `build-verification` skill against the integrated build, output `studio/work/qa-<milestone>.md`.
6. **Fix loop.** Route each defect to its owner, apply the fix, rerun the affected checks. Repeat until criteria pass or are blocked.
7. **Record.** Update `BACKLOG.md` with real evidence paths and any blocked checks. Record the build/commit identifier.
8. **Report and stop:** playable change, validation results, outstanding risks, and a short manual playtest recipe for the user.

## Rules

- A feature is done only when its acceptance criteria have evidence.
- A static review is not a playtest; a headless run is not a visual check; a desktop benchmark is not proof of mobile performance.
- If a check could not run, mark the milestone partially verified and name the exact next verification step.
- Human playtesting remains required for feel, difficulty, and appeal.
