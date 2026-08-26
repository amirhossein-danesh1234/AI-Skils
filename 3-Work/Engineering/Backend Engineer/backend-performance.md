# Backend Performance

## Purpose

Improve service performance without violating correctness or reliability.

## When to Use

Measured latency, throughput, or resource use fails a requirement.

## When Not to Use

Do not cache or parallelize blindly, or change semantics to improve a benchmark.

## Required Inputs

### Required

Representative workload, latency distribution, traces, resource metrics, data volume, and correctness constraints.

### Helpful

Repository, runtime, business rules, contracts, data model, identity context, failure evidence, and deployment constraints.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Bottleneck diagnosis, scoped optimization, before/after evidence, capacity impact, and rollback conditions.

## Operating Principles

Enforce invariants at the authoritative boundary, make retries safe, redact sensitive diagnostics, and verify persisted outcomes rather than status codes alone.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Reproduce the relevant workload and establish latency, errors, and resource baselines.
2. Trace time through application work, queries, network calls, queues, and contention.
3. Change the dominant cause using the least complex effective option.
4. Retest correctness, concurrency, tail latency, and resource saturation under comparable load.

## Decision Rules

- If caching can serve stale permission or financial state, define acceptable staleness before use.
- If concurrency increases pressure on a bottleneck, bound it rather than adding workers indefinitely.

## Validation

- Does improvement persist under realistic skew and data size?
- Are errors, integrity, and operational cost unchanged or explicitly traded off?

## Common Failure Modes

- Average latency hides tail failure: inspect distribution.
- Optimization shifts bottleneck: measure end to end.

## Escalation and Collaboration

Database Engineer optimizes queries; Architect reviews structural limits; DevOps supports safe load measurement.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
