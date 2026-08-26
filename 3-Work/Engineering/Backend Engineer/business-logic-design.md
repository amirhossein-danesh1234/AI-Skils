# Business Logic Design

## Purpose

Implement domain rules so valid transitions preserve required invariants.

## When to Use

A workflow contains consequential rules, state transitions, or money/data effects.

## When Not to Use

Do not infer missing policy from UI behavior or silently choose financial rules.

## Required Inputs

### Required

Approved rules, actors, states, invariants, persistence model, and concurrency expectations.

### Helpful

Repository, runtime, business rules, contracts, data model, identity context, failure evidence, and deployment constraints.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Rule and transition model with validations, side effects, transaction boundaries, and invariant tests.

## Operating Principles

Enforce invariants at the authoritative boundary, make retries safe, redact sensitive diagnostics, and verify persisted outcomes rather than status codes alone.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect approved policy and current implementation, identifying contradictions.
2. Define states, allowed transitions, actor permissions, preconditions, and postconditions.
3. Separate validation from state change and define atomicity for related effects.
4. Test repeated, concurrent, denied, and partially failed operations against invariants.

## Decision Rules

- If a policy affects money or access and is unspecified, ask the owner before implementing that branch.
- If concurrent requests can violate an invariant, enforce it at the authoritative data boundary.

## Validation

- Are invalid transitions rejected and valid ones deterministic?
- Do side effects occur once or reconcile safely after retries?

## Common Failure Modes

- Rules only in UI: enforce server-side.
- Check-then-write race: use appropriate constraints or transaction control.

## Escalation and Collaboration

Product Manager owns policy; Database Engineer owns concurrency mechanisms; QA designs invariant tests.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
