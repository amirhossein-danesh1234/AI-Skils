# Index Design

## Purpose

Choose indexes that improve demonstrated access paths at acceptable write and storage cost.

## When to Use

Queries need supporting indexes or existing indexes impose unnecessary overhead.

## When Not to Use

Do not index every column or assume one engine’s behavior applies to another.

## Required Inputs

### Required

Engine/version, query patterns and plans, table size, data distribution, and write workload.

### Helpful

Database engine/version, schema, constraints, workload evidence, volumes, retention needs, and recovery objectives.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Index proposal with supported queries, key order, selectivity, cost, rollout, and removal criteria.

## Operating Principles

Design from invariants and access patterns; verify query semantics separately from speed and migration safety separately from syntax.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect actual predicates, joins, ordering, and query frequency.
2. Evaluate selectivity, composite key order, covering needs, and existing overlap.
3. Measure candidate plans with representative data and write impact.
4. Plan safe creation and observe usage before retaining or removing indexes.

## Decision Rules

- If an index duplicates a useful prefix without additional benefit, compare consolidation.
- If creation can block critical traffic, use a verified engine-specific online method or maintenance plan.

## Validation

- Does the planner use the index for the intended workload?
- Are write latency, storage, and maintenance costs acceptable?

## Common Failure Modes

- Small test data masks benefit or cost: use realistic distribution.
- Unused index removed too soon: observe a representative workload cycle.

## Escalation and Collaboration

Query-optimization.md diagnoses the query; DevOps coordinates safe deployment; Backend Engineer validates workload.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
