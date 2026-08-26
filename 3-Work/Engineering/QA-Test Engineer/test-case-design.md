# Test Case Design

## Purpose

Create reproducible cases with clear preconditions and pass/fail evidence.

## When to Use

Requirements or defects need executable verification cases.

## When Not to Use

Do not invent expected behavior or duplicate cases merely to increase count.

## Required Inputs

### Required

Requirement, state model, data rules, environment, and risk priority.

### Helpful

Requirements, change diff, architecture, critical journeys, known defects, test environments, and release context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Cases with identifier, purpose, preconditions, data, actions, expected results, cleanup, and traceability.

## Operating Principles

Prioritize impact, likelihood, change exposure, and usage; report skipped, blocked, flaky, and failed tests separately.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect the requirement and identify the observable oracle.
2. Partition inputs and states into meaningful equivalence classes and boundaries.
3. Design normal, negative, permission, repeated, and recovery cases where risk warrants.
4. Define deterministic setup and cleanup and review cases for redundancy.

## Decision Rules

- If several inputs exercise the same behavior, use representative parameterization.
- If the oracle depends on unclear policy, flag the requirement instead of guessing.

## Validation

- Can another tester reproduce the case without hidden context?
- Does failure identify a meaningful violated behavior?

## Common Failure Modes

- Steps without expected result: specify the oracle.
- Environment-dependent flakiness: control state and timing.

## Escalation and Collaboration

Product Manager resolves policy; engineers provide fixtures; acceptance-criteria.md supplies business acceptance.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
