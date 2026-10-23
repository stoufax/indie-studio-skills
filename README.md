# Studio Crew

Seven roles for a small game studio: one lead in the main Codex conversation and six specialist subagents. Marketing and player research participates from discovery through pivot decisions. This is a reusable project configuration, not a running game, hosted service, or installed engine.

## Install into your game repository

1. Extract the ZIP outside your game repository and open the extracted `studio-crew` folder. Show hidden files to see `.codex` and `.agents` (Cmd+Shift+. in macOS Finder).
2. Copy `AGENTS.md`, `.codex`, `.agents`, and `studio` into the root of the game repository. For an empty repository, these can be copied directly.
3. For an existing project, merge rather than overwrite: preserve existing AGENTS.md rules, existing config settings, custom agents, skills in `.agents/skills/`, and studio documents. Codex does not merge two skills with the same name; rename one. Add the supplied `[agents]` keys to an existing table rather than creating a duplicate table. Resolve colliding role names explicitly. The README and VALIDATION.md are setup notes and need not be copied.
4. Start a new local Codex session at the repository root, or open that repository in your Codex client. Complete the normal project trust flow if your client requests it. Do not change permission modes merely to install this pack.
5. Run the first prompt in `studio/PROMPTS.md` to check named-agent discovery. Then run the studio startup prompt. Fill PROJECT.md from your actual project and preferences; the lead can do the repository inspection for you.

## What is included

| Role | Definition | Responsibility |
|---|---|---|
| Lead / producer | AGENTS.md, main conversation | Plan, delegate, integrate, record decisions |
| Game designer | .codex/agents/game_designer.toml | Mechanics, progression, testable design |
| Gameplay engineer | .codex/agents/gameplay_engineer.toml | Combat, movement, enemies, rules |
| Systems engineer | .codex/agents/systems_engineer.toml | Saves, menus, supporting systems |
| Technical artist | .codex/agents/technical_artist.toml | Assets, effects, animation, visual quality |
| Marketing / player research | .codex/agents/marketing_research.toml | Niche discovery, evidence, experiments, pivots |
| QA / performance reviewer | .codex/agents/qa_reviewer.toml | Independent verification and profiling |

### Skills

Twelve [Agent Skills](https://agentskills.io/specification) in `.agents/skills/`, the project skill folder Codex scans and a location the [skills CLI](https://github.com/vercel-labs/skills) used by [skills.sh](https://www.skills.sh/) discovers.

| Skill | Used by | Purpose |
|---|---|---|
| studio-agent-check | Lead | Confirm named custom agents load |
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

The skills are agent-neutral and work in any coding agent that supports Agent Skills, such as Claude Code, Codex, or Cursor. Install them into a project with `npx skills add stoufax/indie-studio-skills -a <agent>` (for example `-a claude-code`); the CLI places them in that agent's skill folder. Agents invoke a skill implicitly from its description, or explicitly by name. Where an agent has no definitions for the specialist roles, or cannot run subagents, the skills fall back to single-agent mode (see task-contract). The five skills that carry a template in `assets/` (task-contract, pivot-review, audience-discovery, audience-experiment, asset-provenance) work when installed alone; the lead workflow skills expect the `studio/` documents. The six role definitions in this pack are Codex files (`.codex/agents/`); other agents need their own role definitions.

The pack also includes a project brief, initial backlog, decision log, evidence ledger, asset register, task/experiment/pivot templates, and six startup/workflow prompts. None contains invented research or completed game work.

## How work flows

Research proposes a reachable audience and a testable promise. Design specifies a small playable response. Engineering and art build separate assigned pieces. The lead integrates. QA checks actual behavior. Human player evidence informs the next iteration or pivot.

Keep at most three specialist threads open concurrently. The six definitions remain available; they are not six permanently running processes. Finished agents are closed and later tasks can spawn new instances. Important context lives in repository documents. This setup does not schedule work or run continuously when the session is closed.

## Compatibility and capabilities

The configuration uses the standalone custom-agent format documented by OpenAI and inherits the parent session's model, reasoning settings, permissions, and tools. No model subscription, API key, or permission override is embedded. Named custom roles require a local Codex client that supports this format. An older client may need updating; do not assume parsing TOML proves runtime compatibility.

Image generation, web research, engine execution, device profiling, and analytics are available only if your environment supplies them. The agent instructions require explicit reporting when a capability is missing. No custom MCP integration is required by this pack.

For ChatGPT Work, local TOML discovery should not be assumed. Use the role descriptions and delegation instructions as task context if that environment cannot load the project definitions. The intended installation target is your local Codex game repository.

## Guardrails that protect useful work

- One owner for each writable file; shared scenes/settings are serialized or integrated by the lead.
- No invented market evidence, playtests, benchmarks, or passed tests.
- Research distinguishes attention, intent, play, returns, and purchases.
- Pivot recommendations preserve counterevidence and uncertainty.
- The user directs material concept changes; ordinary authorized iteration continues autonomously.
- No automatic outreach, ad spend, purchases, or publication.

## Official configuration references

Verified against official documentation on 2026-10-23:

- [Subagents and standalone custom agents](https://learn.chatgpt.com/docs/agent-configuration/subagents)
- [Project instructions with AGENTS.md](https://learn.chatgpt.com/docs/agent-configuration/agents-md)
- [Codex skills](https://developers.openai.com/codex/skills) and [Agent Skills specification](https://agentskills.io/specification)
- [skills CLI: creating skills and discovery paths](https://github.com/vercel-labs/skills/blob/main/docs/creating-skills.md)

See VALIDATION.md for what was checked and what must still be tested in your Codex environment.
