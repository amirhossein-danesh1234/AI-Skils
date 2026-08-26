# Retention Analysis

## Purpose

Measure whether customers return or continue receiving value on the product’s natural cadence.

## When to Use

A team needs to understand sustained use, churn, or reactivation.

## When Not to Use

Do not use daily activity for products whose value naturally recurs monthly or episodically.

## Required Inputs

### Required

Value event, eligible cohort, identity, cadence, observation horizon, and account status rules.

### Helpful

Decision question, event and identity definitions, time windows, source access, instrumentation history, and relevant product changes.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Retention definition and curves, mature cohort comparisons, churn patterns, uncertainty, and product implications.

## Operating Principles

Preserve grain and exposure definitions, reconcile counts, and report null or inconclusive findings as readily as positive ones.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Define the initial and return value events and distinguish user, account, and revenue retention.
2. Choose exact-period, rolling, or bounded retention to match the question and state the interpretation.
3. Handle censoring, reactivation, plan changes, and incomplete observation consistently.
4. Compare segments and investigate value loss using customer evidence.

## Decision Rules

- If cohorts are not equally mature, compare only shared observed ages.
- If contractual lock-in sustains payment without use, report behavioral and commercial retention separately.

## Validation

- Are denominators fixed and late observations handled correctly?
- Does the return event represent value rather than a trivial heartbeat?

## Common Failure Modes

- Immature cohorts appear to churn: handle censoring.
- Usage cadence mismatch: define meaningful return windows.

## Escalation and Collaboration

Product Manager owns retention action; Sales supplies cancellation context; Financial Analyst owns revenue implications.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
