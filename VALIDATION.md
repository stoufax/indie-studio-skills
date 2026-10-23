# Validation record

Date: 2026-10-23

## Completed

- Parsed all seven TOML files with Python 3.12 `tomllib`.
- Checked six distinct specialist names and their required fields against the documented standalone-agent format.
- Confirmed every specialist is named in AGENTS.md and instructed not to spawn further agents.
- Confirmed the main conversation owns the lead role and the concurrency setting allows three specialist threads.
- Checked required project, workflow, evidence, and template files exist and contain valid UTF-8 text.
- Reviewed ownership, audience-evidence, pivot, and verification instructions for consistent responsibilities.
- Packaged all files, including `.codex`, in the ZIP and checked archive integrity and byte-for-byte content equality.

- Skills (added 2026-10-23): checked all twelve `.agents/skills/*/SKILL.md` files against the Agent Skills specification: `name` format and length, `name` equals directory, `description` 1-1024 characters, string-only `metadata`, and every linked `assets/` file exists. Frontmatter was checked with a regex parser (PyYAML not installed) and contains no YAML-breaking `: ` sequences.
- Re-parsed all seven TOML files after adding skill references to each agent's instructions.
- Ran `npx skills add <local folder> --list` (skills CLI, Node 24.19.0): all twelve skills discovered. Installed them with `--skill '*' -a codex` into an empty temporary repository: twelve skills landed in `.agents/skills/` with their `assets/` templates.

## Known maintenance cost

Five templates exist twice: in `studio/` (canonical project copy) and in a skill's `assets/` (so skills work when installed alone). Edit both when a template changes: TASK, PIVOT, EXPERIMENT, EVIDENCE, REGISTER.

## Not run

- Re-packaging the ZIP: the packaging check above predates the skills. A new ZIP must include `.agents`.
- Codex loading the skills and invoking them implicitly or with `$skill-name`.
- Listing on skills.sh: that needs a public GitHub repository and installs through the CLI; this repository is local only and has no remote.
- Codex runtime loading, named-role spawning, and multi-agent handoffs: no Codex executable is installed in the build environment.
- Installation into the user's game repository: no target repository was supplied.
- Engine builds, asset generation, device profiling, and actual audience experiments: no game or engine was selected.

## First check on your machine

After merging the files into your repository and starting a new Codex session, use the read-only agent-discovery prompt in studio/PROMPTS.md. It checks whether `marketing_research` actually loads as a custom agent and reports the tools it can access. Then use the startup prompt to configure the project and produce the first concrete plan.

This is a statically validated starter configuration, not a claim that the studio has already run successfully in your environment.
