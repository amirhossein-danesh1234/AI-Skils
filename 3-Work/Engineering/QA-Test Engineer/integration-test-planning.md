# Integration Test Planning

## Purpose

Verify that real components agree on contracts, persistence, and failure behavior.

## When to Use

A change crosses database, service, queue, or external-adapter boundaries.

## When Not to Use

Do not call a fully mocked boundary an integration test.

## Required Inputs

### Required

Boundary contract, real dependency behavior, test environment, data fixtures, and failure modes.

### Helpful

Requirements, change diff, architecture, critical journeys, known defects, test environments, and release context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Integration plan or tests with setup, contract assertions, persistence checks, cleanup, and failure injection.

## Operating Principles

Prioritize impact, likelihood, change exposure, and usage; report skipped, blocked, flaky, and failed tests separately.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Identify assumptions that unit tests cannot validate across the boundary.
2. Use an appropriate real dependency or contract-faithful controlled substitute and state fidelity limits.
3. Test serialization, transactions, permissions, retries, ordering, and error mapping.
4. Verify authoritative state after operations and isolate test data.

## Decision Rules

- If production uses a database feature absent in the test substitute, use the relevant engine for that check.
- If external calls incur side effects or cost, use an authorized sandbox or deterministic adapter test.

## Validation

- Do tests verify both response and persisted or downstream effects?
- Are isolation, cleanup, and version compatibility controlled?

## Common Failure Modes

- Different engine hides behavior: disclose or fix fidelity.
- Happy-path integration only: exercise partial failure.

## Escalation and Collaboration

Backend and Database Engineers define contracts; DevOps supplies isolated dependencies; Security reviews sensitive test data.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
