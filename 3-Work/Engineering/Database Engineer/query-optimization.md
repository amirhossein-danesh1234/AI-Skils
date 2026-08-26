# Query Optimization

## Purpose

Reduce query cost while preserving exact result semantics.

## When to Use

A measured query is slow or consumes excessive resources.

## When Not to Use

Do not rewrite a query before confirming its correctness and actual bottleneck.

## Required Inputs

### Required

Query, parameters, engine/version, plans, schema, statistics, data distribution, and performance target.

### Helpful

Database engine/version, schema, constraints, workload evidence, volumes, retention needs, and recovery objectives.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Diagnosis, candidate changes, before/after plans and timings, semantic checks, and rollback path.

## Operating Principles

Design from invariants and access patterns; verify query semantics separately from speed and migration safety separately from syntax.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Capture representative parameters and plans without exposing sensitive values.
2. Inspect cardinality estimates, scans, joins, sorts, spills, locks, and returned row volume.
3. Test targeted query, index, statistics, or access-pattern changes one at a time.
4. Compare results and latency under realistic data and concurrency, including worst-case parameters.

## Decision Rules

- If EXPLAIN ANALYZE executes a write or expensive workload, use a safe environment or explicit authorization.
- If a plan regresses for another common parameter set, evaluate overall workload rather than one benchmark.

## Validation

- Are result sets or invariants equivalent before and after?
- Are warm/cold cache and concurrent effects distinguished?

## Common Failure Modes

- Plan cost mistaken for elapsed time: measure.
- Optimization changes null or join semantics: verify edge cases.

## Escalation and Collaboration

Backend Engineer assesses application patterns; index-design.md supports access changes; DevOps monitors operational effects.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
