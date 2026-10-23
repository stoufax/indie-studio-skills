---
name: studio-agent-check
description: Read-only check that the game studio's specialist roles actually load as subagents in the current coding agent (Claude Code, Codex, Cursor, or others) and report the tools they can reach. Use right after installing or merging the studio pack, after updating the coding agent, or when delegating to a named role such as marketing_research fails.
metadata:
  pack: studio-crew
  version: "1.1"
---

# Studio agent check

Confirm that the studio's specialist roles load before relying on them. This check edits nothing.

## When to use

- First session after adding the studio pack to a game repository.
- After updating the coding agent, or when a delegation to a named role fails.

## Steps

1. Identify which coding agent you are running in and where it reads custom subagent definitions, for example `.claude/agents/*.md` in Claude Code or `.codex/agents/*.toml` in Codex. Read the project instructions file (`CLAUDE.md`, `AGENTS.md`, or the equivalent) and every role definition you find. List the role names you expect: `game_designer`, `gameplay_engineer`, `systems_engineer`, `technical_artist`, `marketing_research`, `qa_reviewer`, or their hyphenated forms.
2. Delegate one read-only task to the marketing research role: explain its research and pivot responsibilities and list the tools it can actually access (web, files, shell, image, analytics).
3. Wait for the result, then end that subagent if your tool keeps it open.
4. Report:
   - whether the named role loaded, or whether a generic subagent answered instead;
   - the tools the specialist reported, marked as reported by the agent, not independently verified;
   - whether the studio skills appear in this agent's skill list.
5. Write the outcome into the Tool access table of `studio/PROJECT.md` only if the user asked you to configure the project; otherwise report it in the conversation.

## Rules

- Do not edit game files or other studio documents.
- If no role definitions exist for this agent, or it cannot run subagents, say so plainly. The other studio skills then run in single-agent mode, described in the `task-contract` skill.
- A definition file that parses is not proof that the role loads at runtime.
- Do not mark this check as passed when the delegation did not actually run.
