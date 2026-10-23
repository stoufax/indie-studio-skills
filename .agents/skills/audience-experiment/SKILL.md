---
name: audience-experiment
description: Design an audience validation experiment for a game before it runs - hypothesis, recruitment, variants, primary metric with denominator, sample and time limits, and decision rule - then record results honestly afterwards. Use when testing a game concept, store page, trailer, prototype, or price with players, or when the user asks how to validate demand.
metadata:
  pack: studio-crew
  version: "1.0"
---

# Audience experiment

Fix the decision rule before seeing data, so a result cannot be reinterpreted to fit a preferred concept.

## Template

Use `studio/templates/EXPERIMENT.md` if present; otherwise copy [assets/EXPERIMENT.md](assets/EXPERIMENT.md). Save each experiment as `studio/research/experiment-NNN.md`.

## Before running

1. Name the decision the experiment informs and the hypothesis, citing evidence IDs for and against it.
2. Choose what the signal measures. These are different things and must not be merged:
   - **attention** - views, likes, clicks;
   - **intent** - wishlists, sign-ups;
   - **play** - sessions started and finished;
   - **return** - players coming back;
   - **purchase** - money paid.
3. Define the primary metric with numerator, denominator, and how it is measured.
4. Set the sample target, duration, and stopping rule with a rationale for this question. Do not present an arbitrary threshold as an industry benchmark.
5. Write success, failure, and inconclusive rules now.
6. List biases, confounders, and what the test cannot establish.
7. List the external actions needed (recruiting, posting, spending). Each needs the user's explicit authorization before it happens. Set status to `ready` only when that is recorded.

## After running

1. Record actual dates, sample, source, exclusions, and missing data.
2. Report results with denominators and uncertainty, and where the raw evidence is stored.
3. Note any change from the planned method.
4. List alternative explanations and contradictory observations.
5. Conclude only what was measured. A weak or small sample means `inconclusive`.

## Rules

An unrun experiment has no results. Never fill the After section with expected or simulated numbers; simulated personas are not players.
