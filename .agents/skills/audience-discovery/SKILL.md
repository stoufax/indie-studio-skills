---
name: audience-discovery
description: Research up to three reachable niche audiences for a game - unmet player needs, current alternatives, reachable communities, willingness-to-pay evidence or its absence, differentiation, and counterevidence - and record every claim in the evidence ledger with source and confidence. Use at game discovery, before committing to a concept, or when the user asks who the game is for, what niche to target, or to research competitors and player reviews.
metadata:
  pack: codex-game-studio
  version: "1.0"
---

# Audience discovery

Find who would want this game and why, using real evidence. Output feeds `core-loop-spec`.

## Ledger

Record findings in `studio/research/EVIDENCE.md`. If it is missing, copy [assets/EVIDENCE.md](assets/EVIDENCE.md) there. Use stable IDs (E-001, E-002). If the lead owns the ledger, put proposed entries in your report instead.

## Steps

1. **Start from the decision.** Write the product decision this research informs and the project constraints (platform, scope, team size) from `studio/PROJECT.md`.
2. **Frame hypotheses by behavior, not demographics:** motivations, play context, current alternatives, frustrations, buying behavior, and reachable communities.
3. **Collect sources.** Prioritize player reviews and discussions, public store listings, developer disclosures, and authorized project analytics. Include:
   - direct competitors;
   - small comparable games, not only hits;
   - failed or poorly reviewed examples.
4. **Record each observation** with source URL, published and accessed dates, platform, region where relevant, sampling method, and limitations. When sampling reviews, record counts and denominators.
5. **Separate layers.** For each entry: the observation, your interpretation, and confidence. Label it observation, estimate, or hypothesis.
6. **Write the report** at the assigned path (default `studio/research/discovery.md`) with up to three opportunities. For each: unmet need, evidence and counterevidence IDs, current alternatives, reachable channels, differentiation, production implications, the cheapest useful validation experiment, and reasons the niche may be too small, unreachable, or already served.
7. **Rank** the opportunities with an explained rationale, not false numeric precision.

## Rules

- Review count is not sales; chart rank is not revenue. Estimates need a named method and uncertainty.
- Never invent quotes, players, installs, revenue, retention, or conversion rates.
- Missing web or analytics access is a gap, not negative evidence. Without it, deliver hypotheses and a research plan labeled unvalidated.
- Explain recruitment and selection bias in every sample.
- Reading public sources does not authorize contacting their authors. No outreach, posting, or paid campaigns.
