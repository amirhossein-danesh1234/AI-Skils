# Experiment Analysis

Context: [Product Analyst](README.md).

## Purpose

Estimate an experiment’s effect and decide what the evidence warrants.

## Activate When

A randomized product experiment has results or needs analysis planning.

## Do Not Use When

Observational comparisons need a different causal design; significance alone does not justify launch.

## Required Context

**Needed:** Assignment/exposure logs, planned hypothesis and analysis, outcome data, and randomization unit.

**Can be deferred or bounded:** No pre-analysis plan means deviations and exploratory status must be explicit; it does not permit backdating a plan.

## Workflow

1. Inspect assignment and exposure integrity, sample-ratio mismatch, missing events, and unit contamination.
2. Use the predeclared metric, population, and analysis window; explain any deviations.
3. Estimate effect size and uncertainty at the randomization unit, accounting for clustering and planned multiple comparisons.
4. Check practical value, guardrail harm, novelty, heterogeneity, and operational cost before deciding.

## Analysis Contract and Validity Gates

Before examining treatment outcomes, record assignment unit, analysis unit, eligible population, exposure definition, primary hypothesis, estimand, minimum meaningful effect, guardrails, planned duration or sequential method, and exclusion rules. A user-randomized experiment with repeated events must not treat every event as an independent randomized observation.

Check assignment counts and sample-ratio mismatch, event loss by arm, cross-device identity, exposure leakage, interference, and whether users can enter multiple arms. Distinguish an intention-to-treat analysis from an exposure-restricted analysis and explain the selection risk of the latter. Do not remove inconvenient users based on post-treatment outcomes.

Report absolute and relative effect with units, sample sizes, and uncertainty. Check denominator changes, skewed monetary outcomes, clustering, and multiple comparisons where they affect inference. Use a method appropriate to the design; request statistical support if the design exceeds available competence.

An inconclusive interval is not proof of no effect. A statistically detectable effect may be too small to justify cost or may violate a safety or quality guardrail. Exploratory segments and changed stopping rules must remain labeled exploratory. Record what was preplanned, what changed, and why.

Recommend ship, limited rollout, revise, stop, or further study based on validity, practical value, guardrails, and reversibility. The product owner makes the launch decision; the analyst reports what the experiment can and cannot establish.

## Decision Threshold

Separate statistical uncertainty from the business threshold: show whether the interval includes meaningful benefit, negligible effect, and unacceptable harm. A failed integrity check can block the treatment-effect estimate while still allowing a useful instrumentation finding. Do not selectively extend only disappointing experiments.

## Decision Rules

- If randomization or measurement is invalid, do not interpret a treatment effect until repaired.
- If evidence is inconclusive, report that result; extend only under a valid preplanned or justified sequential method.

## Output Contract

Experiment validity assessment, effect estimates and intervals, guardrails, limitations, and ship/iterate/stop recommendation.

## Quality Gates

- Are exclusions independent of treatment outcomes and missingness assessed?
- Does the decision consider effect magnitude, uncertainty, and guardrails rather than only a p-value?
- Guardrail losses and uncertainty cannot be hidden by a positive primary average.

## Failure Modes

- Repeated peeking inflates false positives: honor stopping design.
- Post-hoc segment winner promoted as confirmed: label exploratory findings.

## Handoffs

Product Manager owns launch choice; engineers confirm assignment; seek statistical expertise for interference, sequential, or complex causal designs.
