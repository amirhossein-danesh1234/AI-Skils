# Database Review

## Purpose

Assess persistence design and changes for integrity, performance, and operational safety.

## When to Use

A schema, query set, or database change needs review.

## When Not to Use

Do not reduce review to normalization or query speed alone.

## Required Inputs

### Required

Diff or schema, access patterns, engine/version, data volume, transactions, and migration plan.

### Helpful

Database engine/version, schema, constraints, workload evidence, volumes, retention needs, and recovery objectives.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Prioritized findings with violated invariant or workload, evidence, remediation, and validation needs.

## Operating Principles

Design from invariants and access patterns; verify query semantics separately from speed and migration safety separately from syntax.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect keys, constraints, cardinality, ownership, and sensitive fields.
2. Trace critical reads and writes through queries, indexes, and transactions.
3. Review migration compatibility, lock exposure, backup, retention, and restore assumptions.
4. Prioritize reachable integrity and availability risks above cosmetic schema preferences.

## Decision Rules

- If a constraint is absent but the application assumes it, require evidence of safe enforcement or add a suitable constraint.
- If production impact cannot be estimated, require rehearsal before approval.

## Validation

- Are findings tied to concrete data or concurrency scenarios?
- Are engine-specific claims verified for the installed version?

## Common Failure Modes

- ORM abstraction hides SQL risk: inspect generated behavior.
- Review ignores migration: assess the path, not only final schema.

## Escalation and Collaboration

Backend, DevOps, and Security owners provide implementation and operational evidence.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
