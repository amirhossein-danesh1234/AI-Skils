# Edge Case Analysis

Context: [QA-Test Engineer](README.md).

## Purpose

Discover high-value boundary and failure scenarios missing from current coverage.

## Activate When

A feature’s happy path is defined but unusual conditions are underexplored.

## Do Not Use When

UX [edge-case-design.md](../../Product/Product%20Designer-UX%20Designer/edge-case-design.md) chooses user behavior; this skill identifies risk and test needs.

## Required Context

**Needed:** States, limits, dependencies, actor permissions, and known coverage.

**Can be deferred or bounded:** Undefined expected behavior becomes a policy question; do not invent an oracle to fill the test matrix.

## Workflow

1. Inspect boundaries in values, sizes, time, identity, concurrency, and lifecycle.
2. Combine plausible stressors such as timeout plus retry or permission change plus cached state.
3. Trace partial completion, duplicate events, cancellation, and recovery.
4. Prioritize by credible impact and identify undefined behavior for owner resolution.

## Reachable Combination

Combine risk-bearing conditions such as timeout plus retry, stale grant plus cached state, or concurrent updates at a limit. Exclude impossible combinations only when constraints demonstrably enforce impossibility. Prioritize data loss, money, and trust-boundary failures over exotic low-consequence inputs.

## Decision Rules

- If a combination is impossible under enforced constraints, do not inflate the test plan with it.
- If an edge case can corrupt data or cross a trust boundary, prioritize it even when rare.

## Output Contract

Prioritized edge-case inventory with trigger, expected invariant, impact, and test approach.

## Quality Gates

- Are cases grounded in reachable states?
- Does every high-risk undefined behavior have an owner?
- Each selected case has a reachable trigger, protected invariant, and expected observable result.

## Failure Modes

- Exotic cases crowd out common failure: rank by risk.
- Edge list without oracle: state the invariant to preserve.

## Handoffs

UX and Product Manager define intended behavior; Backend and Database Engineers validate concurrency mechanisms.
