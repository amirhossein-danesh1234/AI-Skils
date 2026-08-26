# Query Design

Context: [Database Engineer](README.md).

## Purpose

Write queries whose result grain and semantics match the business question.

## Activate When

An application or analysis needs a new data retrieval or mutation query.

## Do Not Use When

[Query-optimization.md](query-optimization.md) improves a correct query; speed cannot compensate for wrong results.

## Required Context

**Needed:** Business question, output grain, schema, permissions, and time/null semantics.

**Can be deferred or bounded:** Optimization can follow a correct baseline; representative edge fixtures are needed before result claims.

## Workflow

1. Define one output row’s meaning and identify authoritative tables.
2. Choose joins, filters, grouping, null handling, and ordering that preserve that grain.
3. Use parameters for values and safe allowlists for dynamic identifiers.
4. Test empty sets, duplicates, missing relations, boundaries, and tenant restrictions.

## Grain Proof

For each join, state one-to-one, one-to-many, or many-to-many expectations and inspect a counterexample. Hand-calculate an empty set, duplicate match, null relation, and time-boundary case. Use an explicit aggregation grain rather than DISTINCT to hide unexplained row multiplication.

## Decision Rules

- If a join multiplies rows, fix the relationship or aggregation rather than hiding it with DISTINCT.
- If pagination needs stable results, define a deterministic order and cursor semantics.

## Output Contract

Query with parameter contract, result definition, edge-case examples, and semantic validation.

## Quality Gates

- Do counts and totals reconcile to independent examples?
- Are permissions, time zones, and null semantics correct?
- Query totals match independent examples and tenant restrictions apply before data is exposed.

## Failure Modes

- Convenient join changes denominator: verify cardinality.
- Unsafe string construction: use parameter binding.

## Handoffs

Backend Engineer validates consumer semantics; Product or Financial Analyst confirms business measures.
