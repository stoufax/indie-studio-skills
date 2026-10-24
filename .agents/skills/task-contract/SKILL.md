---
name: task-contract
description: Write a task contract before delegating work to a studio specialist (game_designer, gameplay_engineer, systems_engineer, technical_artist, marketing_research, qa_reviewer), and check the specialist's handoff against it. Use whenever the lead assigns substantial work to a subagent, splits work across parallel agents, or integrates a returned report.
metadata:
  pack: studio-crew
  version: "1.2"
---

# Task contract

Every delegation gets a written contract so agents never share writable files and every claim in the handoff can be checked.

## Template

Use `studio/templates/TASK.md` if it exists in the repository. Otherwise copy [assets/TASK.md](assets/TASK.md) to that path first.

## Writing the contract

1. **One player outcome or decision.** State what the task supports, not just what to type.
2. **Exact inputs.** Name files and evidence IDs; do not say "see the research".
3. **Exclusive writable paths.** List every path the agent may edit. Shared scenes, engine project settings, package manifests, lockfiles, asset catalogs, and save schemas have one owner; if two tasks need one, serialize them or use separate worktrees with the lead integrating.
4. **Read-only paths.** `PROJECT.md`, `BACKLOG.md`, and `DECISIONS.md` belong to the lead. Specialists propose changes in their handoff.
5. **Interface first.** For parallel implementation, agree the interface (function signatures, events, data shape) before either side starts.
6. **Observable acceptance criteria.** Each criterion must be checkable by running, inspecting, or measuring something.
7. **Validation available.** Say which build, test, or runtime check the agent can actually run.
8. **Stopping point.** Name where the agent stops and reports.

Give reports unique paths under `studio/work/` or `studio/research/`.

## Checking the handoff

1. Inspect the actual changed files, not only the summary.
2. For each criterion, accept only `passed` with evidence, `failed`, or `not run` with the reason.
3. Out-of-scope edits the agent needed must arrive as requests, not as changes. Revert nothing yourself without telling the user.
4. Move proposed shared-document updates into the lead documents yourself.

## Running roles

Each role is defined in `studio/roles/<role>.md`. If a tool registers named subagents from those files, it may spell the names with hyphens (`marketing-research`).

- **With subagents:** start a subagent for each contract and tell it to read and follow `studio/roles/<role>.md`, the project instructions file, and the contract. If the role file is missing, give it the role's skill and the contract instead.
- **Without subagents:** do the task yourself in a separate pass, following the role file or the role's skill and the same contract, and label the handoff `single-agent: <role>`. Keep QA as independent as you can by verifying against the acceptance criteria rather than your own implementation notes, and tell the user that review was not independent.

## Limits

Have at most three specialist tasks in progress at once; end each when its handoff is accepted. Specialists do not delegate further.
