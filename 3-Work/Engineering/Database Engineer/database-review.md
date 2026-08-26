# Database Review

Context: [Database Engineer](README.md).

## Purpose

Assess persistence design and changes for integrity, performance, and operational safety.

## Activate When

A schema, query set, or database change needs review.

## Do Not Use When

Do not reduce review to normalization or query speed alone.

## Required Context

**Needed:** Schema/change, engine/version, workload, invariants, and migration path.

**Can be deferred or bounded:** If representative workload is absent, separate semantic findings from unverified performance claims.

## Workflow

1. Inspect keys, constraints, cardinality, ownership, and sensitive fields.
2. Trace critical reads and writes through queries, indexes, and transactions.
3. Review migration compatibility, lock exposure, backup, retention, and restore assumptions.
4. Prioritize reachable integrity and availability risks above cosmetic schema preferences.

## Three Independent Checks

Review final-state integrity, workload behavior, and transition safety separately. A valid schema can still require an unsafe migration; a fast query can still return the wrong grain. Trace application, jobs, exports, and admin writes that bypass the main service path.

## Decision Rules

- If a constraint is absent but the application assumes it, require evidence of safe enforcement or add a suitable constraint.
- If production impact cannot be estimated, require rehearsal before approval.

## Output Contract

Prioritized findings with violated invariant or workload, evidence, remediation, and validation needs.

## Quality Gates

- Are findings tied to concrete data or concurrency scenarios?
- Are engine-specific claims verified for the installed version?
- No single passing check is used as proof of all three dimensions.

## Failure Modes

- ORM abstraction hides SQL risk: inspect generated behavior.
- Review ignores migration: assess the path, not only final schema.

## Handoffs

Backend, DevOps, and Security owners provide implementation and operational evidence.
