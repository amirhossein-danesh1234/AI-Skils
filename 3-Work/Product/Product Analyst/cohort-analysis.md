# Cohort Analysis

## Purpose

Compare groups with shared starting conditions across time or lifecycle age.

## When to Use

Aggregate trends hide differences between acquisition, launch, or behavior groups.

## When Not to Use

Do not treat post-outcome segmentation as unbiased evidence of causality.

## Required Inputs

### Required

Cohort entry rule, entity grain, outcome, observation period, identity, and relevant exposure.

### Helpful

Decision question, event and identity definitions, time windows, source access, instrumentation history, and relevant product changes.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Cohort table or curves with definitions, sample sizes, maturity, composition, and interpretation.

## Operating Principles

Preserve grain and exposure definitions, reconcile counts, and report null or inconclusive findings as readily as positive ones.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Choose a cohort event that precedes the outcome and matches the decision.
2. Assign entities consistently and define treatment of repeat entry or migration.
3. Align lifecycle age and report incomplete periods explicitly.
4. Compare composition and external changes before attributing differences to product improvements.

## Decision Rules

- If a cohort is defined using future behavior, label selection bias and avoid causal claims.
- If groups are sparse, combine only when meaning remains coherent or report uncertainty.

## Validation

- Can every entity’s assignment be reproduced?
- Are age, calendar effects, and acquisition mix separated?

## Common Failure Modes

- Calendar and lifecycle time confused: label axes.
- Survivor-only data biases results: include eligible non-returners.

## Escalation and Collaboration

Product Manager defines the decision; engineers validate identities; Market or Marketing specialists explain acquisition context.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
