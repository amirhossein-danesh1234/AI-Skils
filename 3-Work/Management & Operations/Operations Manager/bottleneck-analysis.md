# Bottleneck Analysis

## Purpose

Identify the constraint that limits completed throughput or service time.

## When to Use

Queues grow or local improvements do not improve outcomes.

## When Not to Use

Do not equate the busiest person or longest task with the system bottleneck automatically.

## Required Inputs

### Required

Flow map, arrival/completion rates, queues, service times, capacity, and variability.

### Helpful

Actual work samples, process boundaries, volumes, timing, defects, roles, tools, and service expectations.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Constraint diagnosis with evidence, impact, candidate interventions, and measurement plan.

## Operating Principles

Improve end-to-end flow and quality, not one team’s utilization at the expense of downstream queues.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect where work accumulates and how demand varies over time.
2. Compare effective capacity and completion rates across the full flow.
3. Test whether relieving the suspected constraint improves end-to-end output.
4. Consider rework, batching, approvals, and policy constraints before adding resources.

## Decision Rules

- If upstream acceleration only enlarges a downstream queue, stop optimizing that local step.
- If the constraint shifts after intervention, reassess rather than continuing the old fix.

## Validation

- Does evidence distinguish cause from queue symptoms?
- Are throughput and quality measured after the change?

## Common Failure Modes

- Utilization mistaken for bottleneck: inspect flow.
- More staff assumed solution: test policy and rework causes.

## Escalation and Collaboration

Team Manager assesses capacity; Process-optimization.md tests improvements; Project Manager handles bounded dependency work.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
