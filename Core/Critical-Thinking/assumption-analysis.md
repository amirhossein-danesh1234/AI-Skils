# Assumption Analysis

Context: [Critical-Thinking](README.md).

## Purpose

Expose load-bearing assumptions and find decision-flipping tests.

## When to Use

A conclusion or plan depends on untested premises, uncertain inputs or a hidden operating condition.

## Boundary

Values and known constraints are not automatically assumptions to remove.

## Inputs

Proposed conclusion, causal/model structure, known constraints, uncertain inputs and the next commitment.

## Method

1. Extract assumptions at the points where evidence becomes a claim or a plan. Classify empirical assumptions, modeling simplifications, operating dependencies and owner preferences separately.
2. For each material assumption, state its current support and plausible range or alternatives. Test which conclusion or action changes when it fails; discard assumptions irrelevant to the due decision.
3. Identify coupled assumptions and thresholds. A one-at-a-time sensitivity check may miss a combined delay, capacity loss or correlated error.
4. Choose validation, design-around, explicit risk acceptance or monitoring according to decision sensitivity, test cost and time to commitment. Specify an observation that would reverse the recommendation.

## Load-Bearing Test

Rank by impact on the chosen action and exposure before correction, not by uncertainty alone. An uncertain but irrelevant number needs no investigation. A seemingly likely prerequisite can be critical if it gates every benefit. Do not convert a user’s stated preference into a hypothesis to overrule; ask only when preferences conflict or the trade-off is genuinely unstated.

## Output

A compact assumption ledger with support, failure consequence, decision-flip threshold, test/mitigation and review trigger.

## Quality Checks

- The test could actually falsify the premise before the commitment becomes irreversible.
- Unknowns are not assigned convenient midpoint values merely to finish a score.

## Handoffs

[Decision-making](../Decision-Analyst/decision-making.md) weighs the value and delay cost of further information; specialists validate domain assumptions.
