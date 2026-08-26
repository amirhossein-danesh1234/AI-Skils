# Frontend Debugging

Context: [Frontend Engineer](README.md).

## Purpose

Find the cause of an observed client-side defect and verify a scoped correction.

## Activate When

A reproducible UI, routing, state, rendering, or integration failure occurs.

## Do Not Use When

Do not implement a fix during a diagnosis-only task or refactor unrelated code.

## Required Context

**Needed:** Expected/actual behavior, affected route/build, and safe reproduction context.

**Can be deferred or bounded:** Without reproduction, return competing hypotheses and evidence requests rather than a claimed fix.

## Workflow

1. Inspect the current branch, local changes, runtime, server availability, and exact failing route.
2. Reproduce with the smallest relevant state and capture browser errors and network evidence without secrets.
3. Form competing hypotheses and test state, data, rendering, and timing boundaries.
4. Fix only the confirmed cause when authorized, then repeat the original flow and an adjacent regression case.

## Hypothesis Ledger

Record each hypothesis, the observation that distinguishes it, and the result. Check server availability, asset versions, persisted browser state, network contract, and event ordering before editing. A correction must explain both the failing state and a comparable state that works.

## Decision Rules

- If the server is unreachable, restore or diagnose availability before changing route logic.
- If a hypothesis lacks discriminating evidence, test it instead of layering speculative fixes.

## Output Contract

Reproduction, causal explanation, minimal correction if authorized, and regression evidence.

## Quality Gates

- Does the original failure disappear for the demonstrated reason?
- Are stale tabs, cached assets, and persisted client state accounted for?
- The original reproduction and an adjacent regression case are repeated after the scoped correction.

## Failure Modes

- Random edits until success: preserve a causal test.
- Build passes but interaction fails: exercise the actual flow.

## Handoffs

Backend Engineer handles server defects; QA records regression; UI/UX clarify ambiguous expected behavior.
