---
name: studio-agent-check
description: Read-only check that the current coding agent can run the game studio's specialist roles as subagents from the role files in studio/roles/, and report the tools they can reach. Use right after installing or merging the studio pack, after updating the coding agent, or when delegating to a role such as marketing_research fails.
metadata:
  pack: studio-crew
  version: "1.2"
---

# Studio agent check

Confirm that the studio's specialist roles can run as subagents before relying on them. This check edits nothing.

## When to use

- First session after adding the studio pack to a game repository.
- After updating the coding agent, or when a delegation to a role fails.

## Steps

1. Read the project instructions file (`AGENTS.md` or the equivalent your agent reads) and the role files in `studio/roles/`. Expect six: `game_designer`, `gameplay_engineer`, `systems_engineer`, `technical_artist`, `marketing_research`, `qa_reviewer`. Note any named subagent definitions your agent also registered for them.
2. Start one subagent as `marketing_research`, pointing it at `studio/roles/marketing_research.md`, with a read-only task: explain its research and pivot responsibilities and list the tools it can actually access (web, files, shell, image, analytics).
3. Wait for the result, then end that subagent if your tool keeps it open.
4. Report:
   - whether a subagent ran and followed the role file;
   - the tools the specialist reported, marked as reported by the agent, not independently verified;
   - whether the studio skills appear in this agent's skill list.
5. Write the outcome into the Tool access table of `studio/PROJECT.md` only if the user asked you to configure the project; otherwise report it in the conversation.

## Rules

- Do not edit game files or other studio documents.
- If the role files are missing, or this agent cannot run subagents, say so plainly. The other studio skills then run in single-agent mode, described in the `task-contract` skill.
- A role file that exists is not proof that a subagent follows it at runtime.
- Do not mark this check as passed when the delegation did not actually run.
