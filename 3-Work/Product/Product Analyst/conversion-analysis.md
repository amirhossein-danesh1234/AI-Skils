# Conversion Analysis

## Purpose

Explain a change in a defined conversion rate and identify useful tests.

## When to Use

A rate differs across segments, periods, or variants.

## When Not to Use

Funnel analysis locates steps; experiment-analysis.md evaluates randomized treatment effects.

## Required Inputs

### Required

Conversion contract, numerator and denominator, segment mix, time window, and recent changes.

### Helpful

Decision question, event and identity definitions, time windows, source access, instrumentation history, and relevant product changes.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Decomposition of rate change, uncertainty, competing explanations, and recommended next test.

## Operating Principles

Preserve grain and exposure definitions, reconcile counts, and report null or inconclusive findings as readily as positive ones.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Validate the metric definition, tracking, and population before comparing rates.
2. Separate changes within segments from changes in traffic or customer mix.
3. Inspect seasonality, acquisition quality, eligibility, and downstream value.
4. Quantify uncertainty and test plausible mechanisms without claiming causal attribution from association.

## Decision Rules

- If aggregate improvement reverses within segments, report the composition effect.
- If conversion rises while quality or retention falls, assess the net outcome before recommending scale.

## Validation

- Are comparable windows and populations used?
- Do uncertainty and guardrails support the recommendation?

## Common Failure Modes

- Percentage points confused with percent change: report units clearly.
- Correlation presented as cause: propose a discriminating test.

## Escalation and Collaboration

Product Analyst experiment-analysis.md handles experiments; Marketing explains acquisition mix; UX examines behavior.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
