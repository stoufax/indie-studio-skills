# Studio Crew

Seven roles for a small game studio: one lead in the main conversation of your coding agent and six specialist roles it delegates to. Marketing and player research participates from discovery through pivot decisions. This is a reusable project configuration for any coding agent, not a running game, hosted service, or installed engine.

## Install into your game repository

1. Extract the ZIP outside your game repository and open the extracted `studio-crew` folder. Show hidden files to see `.agents` (Cmd+Shift+. in macOS Finder).
2. Copy `AGENTS.md`, `.agents`, and `studio` into the root of the game repository. For an empty repository, these can be copied directly.
3. For an existing project, merge rather than overwrite: preserve existing project instructions, skills, and studio documents. Agents generally do not merge two skills with the same name; rename one. Resolve colliding role names explicitly. The README and VALIDATION.md are setup notes and need not be copied.
4. Make sure your agent reads the files:
   - **Project instructions.** Many agents read `AGENTS.md` directly. If yours reads a different file (Claude Code reads `CLAUDE.md`), add a line importing `@AGENTS.md` to that file, or copy the contents in.
   - **Skills.** `.agents/skills/` is the project skill folder for many agents. If yours uses another folder (Claude Code uses `.claude/skills/`), install with the skills CLI instead: `npx skills add stoufax/indie-studio-skills -a <agent>`, or copy the folders there.
5. Start a new session at the repository root. Complete the normal project trust flow if your agent requests it. Do not change permission modes merely to install this pack.
6. Run the first prompt in `studio/PROMPTS.md` to check that subagents work. Then run the studio startup prompt. Fill PROJECT.md from your actual project and preferences; the lead can do the repository inspection for you.

## What is included

| Role | Definition | Responsibility |
|---|---|---|
| Lead / producer | AGENTS.md, main conversation | Plan, delegate, integrate, record decisions |
| Game designer | studio/roles/game_designer.md | Mechanics, progression, testable design |
| Gameplay engineer | studio/roles/gameplay_engineer.md | Combat, movement, enemies, rules |
| Systems engineer | studio/roles/systems_engineer.md | Saves, menus, supporting systems |
| Technical artist | studio/roles/technical_artist.md | Assets, effects, animation, visual quality |
| Marketing / player research | studio/roles/marketing_research.md | Niche discovery, evidence, experiments, pivots |
| QA / performance reviewer | studio/roles/qa_reviewer.md | Independent verification and profiling |

The role files are plain Markdown with a `name` and `description`, so they do not depend on any one agent's subagent format. The lead starts a generic subagent and points it at the role file and a task contract (see AGENTS.md). If your agent supports named subagent definitions, you can register the roles from these files; keep `studio/roles/` as the source of truth.

### Skills

Twelve [Agent Skills](https://agentskills.io/specification) in `.agents/skills/`, the project skill folder used by many agents and discovered by the [skills CLI](https://github.com/vercel-labs/skills) behind [skills.sh](https://www.skills.sh/).

| Skill | Used by | Purpose |
|---|---|---|
| studio-agent-check | Lead | Confirm subagents can run the studio roles |
| studio-startup | Lead | Configure PROJECT.md and plan the first milestone |
| studio-resume | Lead | Rebuild context from repository records |
| task-contract | Lead | Write delegation contracts and check handoffs |
| milestone-build | Lead | Build, integrate, and verify an approved milestone |
| pivot-review | Lead | Continue / refine / pivot / stop brief |
| audience-discovery | marketing_research | Niche research and evidence ledger |
| audience-experiment | marketing_research | Pre-registered validation experiments |
| core-loop-spec | game_designer | Smallest testable design spec |
| build-verification | qa_reviewer | Independent QA and performance evidence |
| asset-provenance | technical_artist | Asset creation with rights and register entries |
| save-schema-change | systems_engineer | Save data changes with migration and tests |

Install the skills alone with `npx skills add stoufax/indie-studio-skills -a <agent>`; the CLI places them in that agent's skill folder. Agents invoke a skill implicitly from its description, or explicitly by name where supported. A skills-only install does not include `AGENTS.md`, `studio/roles/`, or the other `studio/` documents. The five skills that carry a template in `assets/` (task-contract, pivot-review, audience-discovery, audience-experiment, asset-provenance) work alone; the lead workflow skills expect the `studio/` documents. Without role files the lead uses each role's skill and the task contract as the brief.

The pack also includes a project brief, initial backlog, decision log, evidence ledger, asset register, task/experiment/pivot templates, and six startup/workflow prompts. None contains invented research or completed game work.

## How work flows

Research proposes a reachable audience and a testable promise. Design specifies a small playable response. Engineering and art build separate assigned pieces. The lead integrates. QA checks actual behavior. Human player evidence informs the next iteration or pivot.

Keep at most three specialist subagents in progress at once. The six roles are definitions, not six permanently running processes. Finished subagents are ended and later tasks start new ones. Important context lives in repository documents. This setup does not schedule work or run continuously when the session is closed.

## Compatibility and capabilities

Nothing in the pack is tied to one coding agent. It needs an agent that reads a project instructions file and Agent Skills; subagents are optional. Where the agent cannot run subagents, the lead does each role's task itself in a separate pass (single-agent mode in the `task-contract` skill) and says when QA was not independent. Subagents inherit the parent session's model, permissions, and tools; no model, API key, or permission override is embedded.

Image generation, web research, engine execution, device profiling, and analytics are available only if your environment supplies them. The role instructions require explicit reporting when a capability is missing. No custom MCP integration is required by this pack.

## Guardrails that protect useful work

- One owner for each writable file; shared scenes/settings are serialized or integrated by the lead.
- No invented market evidence, playtests, benchmarks, or passed tests.
- Research distinguishes attention, intent, play, returns, and purchases.
- Pivot recommendations preserve counterevidence and uncertainty.
- The user directs material concept changes; ordinary authorized iteration continues autonomously.
- No automatic outreach, ad spend, purchases, or publication.

## References

- [AGENTS.md project instructions convention](https://agents.md/)
- [Agent Skills specification](https://agentskills.io/specification)
- [skills CLI: supported agents and skill folders](https://github.com/vercel-labs/skills/blob/main/docs/agents.md)
- [skills CLI: creating skills and discovery paths](https://github.com/vercel-labs/skills/blob/main/docs/creating-skills.md)

See VALIDATION.md for what was checked and what must still be tested with your agent.
