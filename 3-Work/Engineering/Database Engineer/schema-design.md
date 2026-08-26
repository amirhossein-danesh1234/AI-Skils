# Schema Design

Context: [Database Engineer](README.md).

## Purpose

Design a physical schema that enforces invariants and supports actual access patterns.

## Activate When

A logical model needs implementation or schema change.

## Do Not Use When

Do not optimize theoretical elegance while ignoring workload, migration, and engine behavior.

## Required Context

**Needed:** Logical model, engine/version, invariants, and access patterns.

**Can be deferred or bounded:** Exact index tuning can follow workload evidence; money precision, identity, tenant scope, and deletion rules need explicit decisions.

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

## Constraint Boundaries

For each invariant, identify whether the engine can enforce it directly or needs a transaction protocol. Test null, duplicate, orphan, cross-tenant relationship, and concurrent creation. Explain valid exceptions instead of encoding a guessed universal rule into an irreversible constraint.

## Decision Rules

- If correctness can be enforced with a database constraint, prefer it over application-only checks.
- If denormalization adds duplicate state, define repair and reconciliation before adoption.

## Output Contract

DDL proposal with keys, constraints, types, relationships, indexes, access rationale, and migration implications.

## Quality Gates

- Do constraints reject invalid and permit valid domain examples?
- Are query plans, write cost, lock behavior, and migration safety considered?
- DDL accepts valid domain examples and rejects the intended invalid ones on the installed engine.

## Failure Modes

- Nullable fields hide undefined states: decide semantics.
- Indexes added without workload: justify each access path.

## Handoffs

Backend Engineer confirms query and write behavior; DevOps reviews rollout; Security checks sensitive-data handling.
