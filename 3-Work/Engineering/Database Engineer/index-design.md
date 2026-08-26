# Index Design

Context: [Database Engineer](README.md).

## Purpose

Choose indexes that improve demonstrated access paths at acceptable write and storage cost.

## Activate When

Queries need supporting indexes or existing indexes impose unnecessary overhead.

## Do Not Use When

Do not index every column or assume one engine’s behavior applies to another.

## Required Context

**Needed:** Actual query patterns/plans, table distribution, engine/version, and write volume.

**Can be deferred or bounded:** Candidate indexes may be proposals until safely measured; deletion requires a representative usage window.

## Workflow

1. Inspect actual predicates, joins, ordering, and query frequency.
2. Evaluate selectivity, composite key order, covering needs, and existing overlap.
3. Measure candidate plans with representative data and write impact.
4. Plan safe creation and observe usage before retaining or removing indexes.

## Index Trade-Off

Compare key order and predicate coverage against real filters, joins, and sorting. Check overlapping indexes and constraints before consolidation. Include write amplification, disk, build locking, maintenance, and rare critical queries; a low usage counter alone does not justify removing a uniqueness constraint.

## Decision Rules

- If an index duplicates a useful prefix without additional benefit, compare consolidation.
- If creation can block critical traffic, use a verified engine-specific online method or maintenance plan.

## Output Contract

Index proposal with supported queries, key order, selectivity, cost, rollout, and removal criteria.

## Quality Gates

- Does the planner use the index for the intended workload?
- Are write latency, storage, and maintenance costs acceptable?
- An index change improves the intended workload without discarding integrity enforcement.

## Failure Modes

- Small test data masks benefit or cost: use realistic distribution.
- Unused index removed too soon: observe a representative workload cycle.

## Handoffs

[Query-optimization.md](query-optimization.md) diagnoses the query; DevOps coordinates safe deployment; Backend Engineer validates workload.
