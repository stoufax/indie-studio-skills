---
name: studio-agent-check
description: Read-only check that the game studio's named custom agents actually load in this Codex client and report the tools they can reach. Use right after installing or merging the studio pack, after updating the Codex client, or when a named role such as marketing_research fails to spawn.
metadata:
  pack: codex-game-studio
  version: "1.0"
---

# Studio agent check

Confirm that the studio's custom roles load before relying on them. This check edits nothing.

## When to use

- First session after copying `AGENTS.md`, `.codex`, `.agents`, and `studio` into a game repository.
- After a Codex client update, or when a delegation to a named role fails.

## Steps

1. Read `AGENTS.md`, `.codex/config.toml`, and every file in `.codex/agents/`. List the role names you expect.
2. Delegate one read-only task to `marketing_research`: explain its research and pivot responsibilities and list the tools it can actually access (web, files, shell, image, analytics).
3. Wait for the result, then close that thread.
4. Report:
   - whether the named custom role loaded, or whether a generic agent answered instead;
   - the tools the specialist reported, marked as reported by the agent, not independently verified;
   - whether the studio skills in `.agents/skills/` appear in the skill list.
5. Write the outcome into the Tool access table of `studio/PROJECT.md` only if the user asked you to configure the project; otherwise report it in the conversation.

## Rules

- Do not edit game files or other studio documents.
- If custom roles are unavailable, say which client limitation blocks them. A parsed TOML file is not proof that the role loads at runtime.
- Do not mark this check as passed when the delegation did not actually run.
