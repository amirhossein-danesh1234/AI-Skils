# Operations Metrics

## Purpose

Define measures that reveal flow, quality, capacity, and service outcomes.

## When to Use

Operations lack useful visibility or local targets distort behavior.

## When Not to Use

Do not maximize utilization or activity counts at the expense of completed value.

## Required Inputs

### Required

Process boundary, customer outcome, events, time semantics, data quality, and decision cadence.

### Helpful

Actual work samples, process boundaries, volumes, timing, defects, roles, tools, and service expectations.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Metric set with definitions, grain, owners, baselines, guardrails, and action rules.

## Operating Principles

Improve end-to-end flow and quality, not one team’s utilization at the expense of downstream queues.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Map customer outcomes to throughput, cycle time, wait time, quality, rework, and capacity as relevant.
2. Define event boundaries and denominators consistently.
3. Choose a small set that exposes trade-offs and downstream effects.
4. Validate collection and specify what action a change triggers.

## Decision Rules

- If a metric can improve by shifting work elsewhere, add an end-to-end guardrail.
- If data is unreliable, fix collection before attaching targets or incentives.

## Validation

- Can operators reproduce the measures and interpret them?
- Are variation and tail outcomes visible?

## Common Failure Modes

- Busy equals effective: measure completed outcomes.
- Average masks service failures: inspect distribution.

## Escalation and Collaboration

Product or Financial Analyst helps measurement; Team Manager prevents misuse in individual evaluation.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
