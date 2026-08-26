# KPI Design

## Purpose

Select a small set of product measures that guide a specific decision.

## When to Use

A team needs useful outcomes and guardrails rather than a dashboard of everything.

## When Not to Use

Do not define success as whichever metric is easiest to increase.

## Required Inputs

### Required

Product objective, user value mechanism, business constraints, available data, and decision cadence.

### Helpful

Decision question, event and identity definitions, time windows, source access, instrumentation history, and relevant product changes.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

KPI set with outcome, drivers, guardrails, definitions, owners, review cadence, and action thresholds.

## Operating Principles

Preserve grain and exposure definitions, reconcile counts, and report null or inconclusive findings as readily as positive ones.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Map the intended user outcome to a plausible product value mechanism.
2. Choose a primary outcome and a few explanatory drivers, not competing primary goals.
3. Add guardrails for harm, quality, cost, and underserved segments.
4. Specify what decisions a change in each measure triggers and validate measurement feasibility.

## Decision Rules

- If a metric can rise while user value deteriorates, add a guardrail or choose a better measure.
- If data is not trustworthy, define instrumentation work before targets.

## Validation

- Does each KPI support an actual decision and have a stable contract?
- Are targets grounded in baseline or explicitly provisional?

## Common Failure Modes

- Vanity metrics mistaken for outcomes: tie to behavior and value.
- Too many KPIs dilute accountability: keep decision ownership clear.

## Escalation and Collaboration

Product Strategist supplies objectives; Product Manager owns actions; engineers validate measurement availability.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
