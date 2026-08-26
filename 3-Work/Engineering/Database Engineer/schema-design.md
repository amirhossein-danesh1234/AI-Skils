# Schema Design

## Purpose

Design a physical schema that enforces invariants and supports actual access patterns.

## When to Use

A logical model needs implementation or schema change.

## When Not to Use

Do not optimize theoretical elegance while ignoring workload, migration, and engine behavior.

## Required Inputs

### Required

Logical model, engine/version, access patterns, volumes, constraints, and retention requirements.

### Helpful

Database engine/version, schema, constraints, workload evidence, volumes, retention needs, and recovery objectives.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

DDL proposal with keys, constraints, types, relationships, indexes, access rationale, and migration implications.

## Operating Principles

Design from invariants and access patterns; verify query semantics separately from speed and migration safety separately from syntax.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect current schema, engine capabilities, and production-like queries.
2. Choose keys, types, nullability, uniqueness, foreign keys, and checks from approved invariants.
3. Normalize to avoid contradictory copies; denormalize only with a measured need and synchronization owner.
4. Map indexes and transaction boundaries to real reads and writes; plan compatible migration.

## Schema Design Record

For each entity, state row grain, primary key rationale, natural uniqueness, attribute types and units, null meaning, relationship cardinality, lifecycle, and deletion or retention behavior. Choose time representation and currency/precision deliberately. Do not use floating-point representations for exact monetary obligations without an explicit justified domain rule.

Map each invariant to its enforcement mechanism: NOT NULL, unique constraint, foreign key, CHECK, transaction protocol, or application rule. Record limitations such as cross-row invariants or engine-specific constraint behavior. Tenant scope must appear consistently in keys, relationships, queries, and permissions where tenancy is part of identity.

List representative access patterns with predicates, joins, ordering, projected fields, expected frequency, and scale. Justify indexes against these patterns and include write and storage cost. Partitioning, denormalization, and specialized storage need an observed or credible workload requirement, not an assumption that every table will become enormous.

Plan the transition from current data: preflight violations, compatible additions, backfill, validation, application cutover, and delayed cleanup. Inspect the installed database version before choosing online DDL or lock-sensitive operations. Rehearse on representative data and capture both correctness and operational effects.

The final record must allow another engineer to explain why valid records are accepted, invalid records are rejected, common queries remain feasible, and existing data can migrate safely. Keep business policy questions with the policy owner rather than encoding guesses as irreversible constraints.

## Decision Rules

- If correctness can be enforced with a database constraint, prefer it over application-only checks.
- If denormalization adds duplicate state, define repair and reconciliation before adoption.

## Validation

- Do constraints reject invalid and permit valid domain examples?
- Are query plans, write cost, lock behavior, and migration safety considered?

## Common Failure Modes

- Nullable fields hide undefined states: decide semantics.
- Indexes added without workload: justify each access path.

## Escalation and Collaboration

Backend Engineer confirms query and write behavior; DevOps reviews rollout; Security checks sensitive-data handling.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
