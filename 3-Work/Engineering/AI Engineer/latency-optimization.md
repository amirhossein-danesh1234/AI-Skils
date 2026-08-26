# Latency Optimization

Context: [AI Engineer](README.md).

## Purpose

Reduce end-to-end AI task delay while preserving the required behavior.

## Activate When

Measured user-visible latency exceeds a target or a proposed workflow risks missing its deadline.

## Do Not Use When

Streaming improves time to first output but does not necessarily improve time to a correct completed task.

## Required Context

**Needed:** Representative traces, latency target, task-quality gates, traffic distribution, and provider limits.

**Can be deferred or bounded:** Set a baseline before choosing caching, concurrency, prompt reduction, or a smaller model.

## Workflow

1. Measure queueing, retrieval, context assembly, model first/last token, tool calls, validation, retries, fallback, and review where relevant. Inspect tail and cold-start behavior.
2. Find the dominant sequential path. Compare fewer calls, narrower context/output, faster evaluated model, parallel independent reads, caching, or precomputation.
3. Check cache identity, tenant scope, freshness, and permission invalidation; never cache a side effect as though it were a pure response.
4. Apply one justified change and rerun task quality, severe errors, cost, and tail latency under comparable load, including provider slowdown.
5. Define cancellation/deadlines and degraded routes. Retain the change only if measured user benefit exceeds added complexity.

## Decision Rules

- If concurrency shifts latency into provider throttling or downstream overload, bound it.
- If early streamed content can mislead before validation, buffer consequential output or clearly separate provisional from verified results.

## Output Contract

Latency breakdown, optimization hypothesis, before/after distributions, quality/cost checks, and rollout/reversal conditions.

## Quality Gates

- The same successful-task definition is used before and after.
- Slow and failed runs remain in latency and deadline reporting.

## Failure Modes

- First-token speed hides long tool chains.
- Benchmark excludes quota failures and retries.

## Handoffs

DevOps checks load/quotas; model-selection compares candidates; context-engineering trims context; fallback-design controls deadline exhaustion.
