# Validation record

Date: 2026-10-24

## Completed

- Role definitions: six agent-neutral role files in `studio/roles/`, converted from the earlier tool-specific definitions without changing their instructions except to refer to "the project instructions file" and to forbid further delegation. Checked each has `name` equal to its file name and a `description` of 1-1024 characters.
- Confirmed every specialist is named in AGENTS.md, which states how the lead starts a role as a subagent, the limit of three specialists in progress, and the single-agent fallback.
- Skills: checked all twelve `.agents/skills/*/SKILL.md` files against the Agent Skills specification: `name` format, `name` equals directory, `description` 1-1024 characters with no YAML-breaking `: ` sequences, and every linked `assets/` file exists. Frontmatter was checked with a regex parser (PyYAML not installed).
- Ran `npx skills add . --list` (skills CLI, Node 24.19.0, public npm registry): all twelve skills discovered; the role files are not picked up as skills.
- Searched the pack for references to a specific coding agent's configuration format; none remain. Claude Code is named only where its different instructions file and skill folder need an install note.
- Checked required project, workflow, evidence, and template files exist and contain valid UTF-8 text.

## Known maintenance cost

Five templates exist twice: in `studio/` (canonical project copy) and in a skill's `assets/` (so skills work when installed alone). Edit both when a template changes: TASK, PIVOT, EXPERIMENT, EVIDENCE, REGISTER.

## Not run

- Re-packaging the ZIP: no ZIP has been built since `.agents` was added and `.codex` was removed.
- Any coding agent loading the skills and invoking them implicitly or by name.
- A live subagent following a role file, and multi-agent handoffs, in any agent.
- `npx skills add stoufax/indie-studio-skills` from GitHub after this change. The listing on https://www.skills.sh/stoufax/indie-studio-skills shows all twelve skills from the previous version.
- Installation into the user's game repository: no target repository was supplied.
- Engine builds, asset generation, device profiling, and actual audience experiments: no game or engine was selected.

## First check on your machine

After merging the files into your repository and starting a new session in your coding agent, use the read-only check in prompt 1 of studio/PROMPTS.md (the `studio-agent-check` skill). It checks whether a subagent can run as `marketing_research` from its role file and reports the tools it can access. Then use the startup prompt to configure the project and produce the first concrete plan.

This is a statically validated starter configuration, not a claim that the studio has already run successfully in your environment.
