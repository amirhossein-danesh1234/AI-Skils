# Business Logic Design

Context: [Backend Engineer](README.md).

## Purpose

Implement domain rules so valid transitions preserve required invariants.

## Activate When

A workflow contains consequential rules, state transitions, or money/data effects.

## Do Not Use When

Do not infer missing policy from UI behavior or silently choose financial rules.

## Required Context

**Needed:** Approved rules, lifecycle states, actors, and persistence boundaries.

**Can be deferred or bounded:** Undecided policy remains an explicit transition gap; do not infer it from present UI behavior.

## Workflow

1. Inspect approved policy and current implementation, identifying contradictions.
2. Define states, allowed transitions, actor permissions, preconditions, and postconditions.
3. Separate validation from state change and define atomicity for related effects.
4. Test repeated, concurrent, denied, and partially failed operations against invariants.

## Rule Table

Express precondition, actor authority, transition, postcondition, and side effects for each meaningful event. Include boundary amounts, rounding/time rules where relevant, and compensating behavior after partial failure. Generate tests from invariants rather than duplicating implementation calculations as the expected result.

## Decision Rules

- If a policy affects money or access and is unspecified, ask the owner before implementing that branch.
- If concurrent requests can violate an invariant, enforce it at the authoritative data boundary.

## Output Contract

Rule and transition model with validations, side effects, transaction boundaries, and invariant tests.

## Quality Gates

- Are invalid transitions rejected and valid ones deterministic?
- Do side effects occur once or reconcile safely after retries?
- Invalid concurrent or repeated transitions are rejected atomically or reconciled safely.

## Failure Modes

- Rules only in UI: enforce server-side.
- Check-then-write race: use appropriate constraints or transaction control.

## Handoffs

Product Manager owns policy; Database Engineer owns concurrency mechanisms; QA designs invariant tests.
