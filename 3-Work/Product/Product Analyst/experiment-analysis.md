# Experiment Analysis

## Purpose

Estimate an experiment’s effect and decide what the evidence warrants.

## When to Use

A randomized product experiment has results or needs analysis planning.

## When Not to Use

Observational comparisons need a different causal design; significance alone does not justify launch.

## Required Inputs

### Required

Assignment unit, hypothesis, primary metric, guardrails, randomization, exposure, sample plan, and stopping rule.

### Helpful

Decision question, event and identity definitions, time windows, source access, instrumentation history, and relevant product changes.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Experiment validity assessment, effect estimates and intervals, guardrails, limitations, and ship/iterate/stop recommendation.

## Operating Principles

Preserve grain and exposure definitions, reconcile counts, and report null or inconclusive findings as readily as positive ones.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

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

## Decision Rules

- If randomization or measurement is invalid, do not interpret a treatment effect until repaired.
- If evidence is inconclusive, report that result; extend only under a valid preplanned or justified sequential method.

## Validation

- Are exclusions independent of treatment outcomes and missingness assessed?
- Does the decision consider effect magnitude, uncertainty, and guardrails rather than only a p-value?

## Common Failure Modes

- Repeated peeking inflates false positives: honor stopping design.
- Post-hoc segment winner promoted as confirmed: label exploratory findings.

## Escalation and Collaboration

Product Manager owns launch choice; engineers confirm assignment; seek statistical expertise for interference, sequential, or complex causal designs.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
