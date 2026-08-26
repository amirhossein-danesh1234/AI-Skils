# Unit Test Planning

## Purpose

Select isolated tests for domain rules and local behavior.

## When to Use

A code change needs fast regression confidence at the unit boundary.

## When Not to Use

Do not mock away the behavior under test or assert private implementation details.

## Required Inputs

### Required

Changed unit, public contract, invariants, dependencies, and existing test conventions.

### Helpful

Requirements, change diff, architecture, critical journeys, known defects, test environments, and release context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Unit test plan or cases covering meaningful inputs, outputs, errors, and state transitions.

## Operating Principles

Prioritize impact, likelihood, change exposure, and usage; report skipped, blocked, flaky, and failed tests separately.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect the unit’s responsibility and separate pure behavior from external effects.
2. Choose representative normal, boundary, and invalid cases from the contract.
3. Use real lightweight dependencies where practical and mock only genuine external boundaries.
4. Verify tests fail for a plausible defect and remain independent of execution order.

## Decision Rules

- If correctness depends on database or protocol semantics, add an integration test rather than over-mocking.
- If a test only repeats implementation logic, replace it with an independent expected result.

## Validation

- Are tests deterministic and focused on public behavior?
- Would a meaningful regression be detected without brittle coupling?

## Common Failure Modes

- Mock call count mistaken for behavior: assert outcomes.
- One test per line: focus on invariant coverage.

## Escalation and Collaboration

Implementation owner provides seams; integration-test-planning.md covers real boundaries.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
