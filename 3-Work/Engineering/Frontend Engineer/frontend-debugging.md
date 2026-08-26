# Frontend Debugging

## Purpose

Find the cause of an observed client-side defect and verify a scoped correction.

## When to Use

A reproducible UI, routing, state, rendering, or integration failure occurs.

## When Not to Use

Do not implement a fix during a diagnosis-only task or refactor unrelated code.

## Required Inputs

### Required

Expected and actual behavior, reproduction context, logs, recent changes, and repository state.

### Helpful

Repository instructions, approved UI and behavior, runtime versions, API contracts, existing tests, and supported devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Reproduction, causal explanation, minimal correction if authorized, and regression evidence.

## Operating Principles

Follow existing conventions, keep state minimal, test realistic interactions, and distinguish compilation from verified user behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect the current branch, local changes, runtime, server availability, and exact failing route.
2. Reproduce with the smallest relevant state and capture browser errors and network evidence without secrets.
3. Form competing hypotheses and test state, data, rendering, and timing boundaries.
4. Fix only the confirmed cause when authorized, then repeat the original flow and an adjacent regression case.

## Decision Rules

- If the server is unreachable, restore or diagnose availability before changing route logic.
- If a hypothesis lacks discriminating evidence, test it instead of layering speculative fixes.

## Validation

- Does the original failure disappear for the demonstrated reason?
- Are stale tabs, cached assets, and persisted client state accounted for?

## Common Failure Modes

- Random edits until success: preserve a causal test.
- Build passes but interaction fails: exercise the actual flow.

## Escalation and Collaboration

Backend Engineer handles server defects; QA records regression; UI/UX clarify ambiguous expected behavior.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
