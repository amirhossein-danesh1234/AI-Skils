# API Integration

## Purpose

Connect the UI to a server contract with correct data and failure behavior.

## When to Use

A frontend needs to load or mutate remote data.

## When Not to Use

Do not invent backend fields, treat UI authorization as security, or retry unsafe mutations blindly.

## Required Inputs

### Required

API contract, auth mechanism, response examples, error semantics, and UI states.

### Helpful

Repository instructions, approved UI and behavior, runtime versions, API contracts, existing tests, and supported devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Integration with typed or validated boundaries, loading/error states, cancellation, cache behavior, and contract tests.

## Operating Principles

Follow existing conventions, keep state minimal, test realistic interactions, and distinguish compilation from verified user behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect actual endpoints, payloads, identity handling, pagination, and version compatibility.
2. Map server data to UI needs without leaking transport details through every component.
3. Handle timeouts, cancellation, unauthorized responses, empty results, and validation errors.
4. Define cache invalidation and mutation retry behavior; verify persisted outcomes after refresh.

## Decision Rules

- If a mutation lacks idempotency guarantees, do not automatically repeat it after ambiguous failure.
- If the contract differs from the specification, surface the discrepancy rather than guessing.

## Validation

- Do successful and failed flows produce correct visible and persisted state?
- Are credentials excluded from URLs, logs, and unintended storage?

## Common Failure Modes

- HTTP success treated as business success: inspect outcome fields.
- Stale cache hides a failed mutation: verify authoritative refresh.

## Escalation and Collaboration

Backend Engineer resolves contract issues; Security reviews token handling; QA tests end-to-end behavior.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
