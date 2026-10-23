---
name: pivot-review
description: Run a milestone review that ends in a continue, refine, pivot, or stop recommendation, combining independent assessments from marketing_research, game_designer, and qa_reviewer into a pivot brief with counterevidence, cost, and the next discriminating test. Use at milestone reviews, after an audience experiment completes, or when the user asks whether to pivot or change the game's direction.
metadata:
  pack: studio-crew
  version: "1.0"
---

# Pivot review

Produce a recommendation the user can decide on. A recommendation is not authorization to implement a material pivot.

## Template

Use `studio/templates/PIVOT.md` if present; otherwise copy [assets/PIVOT.md](assets/PIVOT.md) there. Save the brief as `studio/work/pivot-<milestone>.md`.

## Steps

1. **Gather actual results.** Read the milestone's experiment files, QA report, and cited evidence IDs. List what is missing.
2. **Three independent assessments**, delegated with `task-contract`, each to its own report path:
   - `marketing_research`: audience evidence, positioning, channel and business-model explanations.
   - `game_designer`: which experience changes could explain the results, and the smallest prototype that tells competing explanations apart.
   - `qa_reviewer`: whether bugs, crashes, or performance could explain poor player results.
   Do not show one assessor another's conclusion before they report.
3. **Fill the brief.** Separate what players did from what they said. Fill every option row - continue, refine, pivot, stop - with evidence for and against, cost, reusable work, next test, and main risk.
4. **Preserve disagreement.** Quote where the assessments conflict; do not average them away.
5. **Recommend** with a confidence level and a review trigger. Record the recommendation in `DECISIONS.md` as proposed.
6. **Ask the user** to decide any material change to audience, core loop, platform, or business model, unless they already authorized it.

## Rules

- Weak or small samples are inconclusive, not a forced pivot.
- Do not blame the concept automatically; compare audience, positioning, core-loop, and business-model explanations.
- No fabricated players, quotes, or metrics.
