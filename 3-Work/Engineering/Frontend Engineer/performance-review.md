# Frontend Engineer — Performance Review

Context: [Frontend Engineer](README.md).

## Purpose

Identify and correct frontend performance bottlenecks using representative evidence.

## Activate When

Users experience slow load, interaction, rendering, or resource use.

## Do Not Use When

Do not optimize based on intuition alone or sacrifice correctness for a synthetic score.

## Required Context

**Needed:** Affected journey, representative device/network, build mode, and measurements.

**Can be deferred or bounded:** Targets can be provisional for diagnosis; optimization benefit requires comparable before/after evidence.

## Workflow

1. Reproduce the user-visible delay in a representative production-like build.
2. Measure loading, main-thread work, rendering, network, memory, and interaction timing as relevant.
3. Isolate the dominant bottleneck and distinguish app cost from backend or network delay.
4. Apply the smallest justified change and remeasure the same scenario with functional regression checks.

## User Delay Budget

Decompose delay into network, server, parsing, scripting, rendering, layout, and interaction work as relevant. Test realistic content and slow devices; inspect long tasks and repeated renders before adding memoization. Preserve a record of measurement conditions so a faster machine cannot masquerade as improvement.

## Decision Rules

- If the backend dominates latency, route the finding rather than obscuring it with UI tricks.
- If an optimization increases maintenance cost with negligible user benefit, defer it.

## Output Contract

Performance findings with baseline, bottleneck evidence, proposed fixes, trade-offs, and before/after checks.

## Quality Gates

- Are comparisons made under comparable conditions and repeated enough to avoid noise?
- Are slow devices, content extremes, and regression risks covered?
- The optimization reduces the demonstrated user delay without breaking behavior or accessibility.

## Failure Modes

- Development build benchmark: use relevant build conditions.
- Average score hides a bad interaction: measure the actual journey.

## Handoffs

Backend Engineer investigates server delays; UI/UX assess perceived feedback; QA verifies behavior after optimization.
