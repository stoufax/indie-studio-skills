# Studio prompts

Each prompt has a matching skill in `.agents/skills/`. In Codex you can also start one directly, for example `$studio-startup`: 1 `studio-agent-check`, 2 `studio-startup`, 3 `audience-discovery` then `core-loop-spec`, 4 `milestone-build`, 5 `pivot-review`, 6 `studio-resume`.

## 1. Confirm agent discovery (no game edits)

Act as studio lead. Read AGENTS.md and the custom agent definitions. Delegate a read-only check to marketing_research: explain its research and pivot responsibilities and what tools it can actually access. Wait for its result, close its thread, and report whether the named custom role loaded. Do not edit game files. If custom roles are unavailable, explain the client limitation rather than pretending the check passed.

## 2. Start the studio

Act as studio lead using this project's AGENTS.md. Inspect the repository and fill verified facts in studio/PROJECT.md. Ask only for missing decisions that block progress. Delegate audience discovery to marketing_research and technical feasibility inspection to systems_engineer in parallel with separate report paths. Use up to three specialists at once. Have game_designer use their findings to propose the smallest playable experiment. Update the backlog and decision log. Stop with a concrete prototype plan; do not build an unchosen game.

## 3. Find an audience before committing

Have marketing_research investigate up to three niche audiences that fit the project's constraints. Use current player evidence, comparable small games, and counterexamples. Report unmet needs, reachable communities, current alternatives, willingness-to-pay evidence or its absence, and differentiation. Have game_designer translate the strongest hypotheses into small playable experiments. Distinguish hypotheses from validated findings. Do not contact anyone or run paid campaigns.

## 4. Build the approved milestone

Implement the next approved playable milestone. As lead, define acceptance criteria and task ownership first. Delegate independent gameplay, systems, or art work only after agreeing interfaces. Integrate the changes and have qa_reviewer verify the integrated result. Fix observed failures and rerun affected checks. Update the backlog with actual evidence. Stop at the milestone and report what needs my playtesting.

## 5. Review a possible pivot

Review the current milestone and actual experiment results. Have marketing_research assess audience evidence and game_designer assess experience changes independently. Have qa_reviewer identify whether bugs or performance could explain poor player results. Produce a pivot brief with continue/refine/pivot/stop options, counterevidence, cost, reusable work, and the next cheapest discriminating test. Do not implement a material pivot until my decision unless I already authorized it.

## 6. Resume later

Read PROJECT.md, BACKLOG.md, DECISIONS.md, and relevant evidence. Inspect the working tree. Summarize the active milestone, verified results, and unresolved assumptions. Continue the next ready task within existing authorization; use specialist agents where their tasks are independent. Do not recreate completed work or infer that an unfinished experiment has results.
