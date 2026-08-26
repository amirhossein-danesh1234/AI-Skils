# Performance Review

## Purpose

Identify and correct frontend performance bottlenecks using representative evidence.

## When to Use

Users experience slow load, interaction, rendering, or resource use.

## When Not to Use

Do not optimize based on intuition alone or sacrifice correctness for a synthetic score.

## Required Inputs

### Required

Affected journey, devices, network conditions, measurements, build mode, and recent changes.

### Helpful

Repository instructions, approved UI and behavior, runtime versions, API contracts, existing tests, and supported devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Performance findings with baseline, bottleneck evidence, proposed fixes, trade-offs, and before/after checks.

## Operating Principles

Follow existing conventions, keep state minimal, test realistic interactions, and distinguish compilation from verified user behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Reproduce the user-visible delay in a representative production-like build.
2. Measure loading, main-thread work, rendering, network, memory, and interaction timing as relevant.
3. Isolate the dominant bottleneck and distinguish app cost from backend or network delay.
4. Apply the smallest justified change and remeasure the same scenario with functional regression checks.

## Decision Rules

- If the backend dominates latency, route the finding rather than obscuring it with UI tricks.
- If an optimization increases maintenance cost with negligible user benefit, defer it.

## Validation

- Are comparisons made under comparable conditions and repeated enough to avoid noise?
- Are slow devices, content extremes, and regression risks covered?

## Common Failure Modes

- Development build benchmark: use relevant build conditions.
- Average score hides a bad interaction: measure the actual journey.

## Escalation and Collaboration

Backend Engineer investigates server delays; UI/UX assess perceived feedback; QA verifies behavior after optimization.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
