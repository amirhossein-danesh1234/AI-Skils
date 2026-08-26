# Query Optimization

Context: [Database Engineer](README.md).

## Purpose

Reduce query cost while preserving exact result semantics.

## Activate When

A measured query is slow or consumes excessive resources.

## Do Not Use When

Do not rewrite a query before confirming its correctness and actual bottleneck.

## Required Context

**Needed:** Correct query, representative parameters, engine/version, execution plan, and target.

**Can be deferred or bounded:** Costly execution plans must run in a safe scope; static EXPLAIN is not measured elapsed time.

## Workflow

1. Capture representative parameters and plans without exposing sensitive values.
2. Inspect cardinality estimates, scans, joins, sorts, spills, locks, and returned row volume.
3. Test targeted query, index, statistics, or access-pattern changes one at a time.
4. Compare results and latency under realistic data and concurrency, including worst-case parameters.

## Plan Comparison

Compare estimated and actual cardinalities, scanned versus returned rows, sort spills, waits, and lock contention. Retain result-equivalence fixtures through each change. Test both common and skewed parameter values; a local improvement that regresses the dominant workload is not a win.

## Decision Rules

- If EXPLAIN ANALYZE executes a write or expensive workload, use a safe environment or explicit authorization.
- If a plan regresses for another common parameter set, evaluate overall workload rather than one benchmark.

## Output Contract

Diagnosis, candidate changes, before/after plans and timings, semantic checks, and rollback path.

## Quality Gates

- Are result sets or invariants equivalent before and after?
- Are warm/cold cache and concurrent effects distinguished?
- Before/after evidence uses comparable data, cache conditions, and concurrency.

## Failure Modes

- Plan cost mistaken for elapsed time: measure.
- Optimization changes null or join semantics: verify edge cases.

## Handoffs

Backend Engineer assesses application patterns; [index-design.md](index-design.md) supports access changes; DevOps monitors operational effects.
