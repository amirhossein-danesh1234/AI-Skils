# Insight Synthesis

Context: [Data-Analyst](README.md).

## Purpose

Translate findings into bounded interpretations and decision implications.

## When to Use

Several analytical findings need one decision-relevant interpretation without losing uncertainty.

## Boundary

Recommendation authority stays with the actual decision owner.

## Inputs

Verified results, metric contracts, design limitations, decision question and credible alternative explanations.

## Method

1. Separate observation, interpretation and proposed action. For each finding, retain magnitude, denominator, uncertainty and relevant population/time scope.
2. Reconcile apparent conflicts caused by different definitions, segments, maturity or aggregation. Preserve unresolved disagreement instead of averaging incompatible results.
3. Rank findings by decision consequence and reliability, not novelty or statistical significance alone. Identify which outcome is practically material under the owner’s criteria.
4. Compare plausible mechanisms and what evidence would distinguish them. Link any proposed action to an explicit assumption and test rather than presenting correlation as instruction.
5. Write a concise conclusion with what can be decided now, what cannot, and the smallest additional analysis that could change the decision.

## Claim Ladder

Move from “observed in this sample” to “likely in the target population” to “caused by” only when design supports each step. A plausible story is an interpretation, not a measured result. When findings are inconclusive, recommend a bounded decision under uncertainty or a better measurement plan; do not invent an insight to justify the analysis effort.

## Output

Prioritized findings, supported interpretation, competing explanation, decision implications and evidence/owner gates.

## Quality Checks

- Every action recommendation is distinguishable from a data result and carries its assumption.
- Headline and summary preserve material caveats found in the detailed analysis.

## Handoffs

[Decision-Analyst](../Decision-Analyst/README.md) integrates preferences and alternatives; [Writer](../Writer/README.md) improves communication without increasing certainty.
