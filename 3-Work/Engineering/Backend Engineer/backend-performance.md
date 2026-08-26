# Backend Performance

Context: [Backend Engineer](README.md).

## Purpose

Improve service performance without violating correctness or reliability.

## Activate When

Measured latency, throughput, or resource use fails a requirement.

## Do Not Use When

Do not cache or parallelize blindly, or change semantics to improve a benchmark.

## Required Context

**Needed:** Measured workload, latency/resource baseline, and correctness constraints.

**Can be deferred or bounded:** No production load testing without scope; a safe representative environment can establish a bounded result.

## Workflow

1. Reproduce the relevant workload and establish latency, errors, and resource baselines.
2. Trace time through application work, queries, network calls, queues, and contention.
3. Change the dominant cause using the least complex effective option.
4. Retest correctness, concurrency, tail latency, and resource saturation under comparable load.

## Saturation Analysis

Separate service time from queue wait, inspect connection pools and fan-out, and measure tail latency under contention. If a cache is proposed, define key, tenant scope, invalidation, freshness, and failure behavior. Limit retries and concurrency so optimization does not amplify a downstream outage.

## Decision Rules

- If caching can serve stale permission or financial state, define acceptable staleness before use.
- If concurrency increases pressure on a bottleneck, bound it rather than adding workers indefinitely.

## Output Contract

Bottleneck diagnosis, scoped optimization, before/after evidence, capacity impact, and rollback conditions.

## Quality Gates

- Does improvement persist under realistic skew and data size?
- Are errors, integrity, and operational cost unchanged or explicitly traded off?
- The change preserves authorization and business invariants under the same concurrent workload.

## Failure Modes

- Average latency hides tail failure: inspect distribution.
- Optimization shifts bottleneck: measure end to end.

## Handoffs

Database Engineer optimizes queries; Architect reviews structural limits; DevOps supports safe load measurement.
