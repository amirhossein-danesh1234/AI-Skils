# Query Design

## Purpose

Write queries whose result grain and semantics match the business question.

## When to Use

An application or analysis needs a new data retrieval or mutation query.

## When Not to Use

Query-optimization.md improves a correct query; speed cannot compensate for wrong results.

## Required Inputs

### Required

Question, schema, expected grain, filters, permissions, time semantics, and representative data.

### Helpful

Database engine/version, schema, constraints, workload evidence, volumes, retention needs, and recovery objectives.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Query with parameter contract, result definition, edge-case examples, and semantic validation.

## Operating Principles

Design from invariants and access patterns; verify query semantics separately from speed and migration safety separately from syntax.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Define one output row’s meaning and identify authoritative tables.
2. Choose joins, filters, grouping, null handling, and ordering that preserve that grain.
3. Use parameters for values and safe allowlists for dynamic identifiers.
4. Test empty sets, duplicates, missing relations, boundaries, and tenant restrictions.

## Decision Rules

- If a join multiplies rows, fix the relationship or aggregation rather than hiding it with DISTINCT.
- If pagination needs stable results, define a deterministic order and cursor semantics.

## Validation

- Do counts and totals reconcile to independent examples?
- Are permissions, time zones, and null semantics correct?

## Common Failure Modes

- Convenient join changes denominator: verify cardinality.
- Unsafe string construction: use parameter binding.

## Escalation and Collaboration

Backend Engineer validates consumer semantics; Product or Financial Analyst confirms business measures.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
