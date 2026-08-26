# Test Case Design

Context: [QA-Test Engineer](README.md).

## Purpose

Create reproducible cases with clear preconditions and pass/fail evidence.

## Activate When

Requirements or defects need executable verification cases.

## Do Not Use When

Do not invent expected behavior or duplicate cases merely to increase count.

## Required Context

**Needed:** Requirement/invariant, observable expected result, state, and environment.

**Can be deferred or bounded:** Tooling can follow the case design; unclear business rules cannot be resolved by test-author preference.

## Workflow

1. Inspect the requirement and identify the observable oracle.
2. Partition inputs and states into meaningful equivalence classes and boundaries.
3. Design normal, negative, permission, repeated, and recovery cases where risk warrants.
4. Define deterministic setup and cleanup and review cases for redundancy.

## Discriminating Case

Choose a passing example and the smallest change that should fail it. Use equivalence classes and boundaries to avoid redundant cases, and define setup/cleanup explicitly. For concurrency or asynchronous behavior, control the relevant ordering rather than hoping a stress loop happens to trigger the defect.

## Decision Rules

- If several inputs exercise the same behavior, use representative parameterization.
- If the oracle depends on unclear policy, flag the requirement instead of guessing.

## Output Contract

Cases with identifier, purpose, preconditions, data, actions, expected results, cleanup, and traceability.

## Quality Gates

- Can another tester reproduce the case without hidden context?
- Does failure identify a meaningful violated behavior?
- A plausible incorrect implementation fails the case for the intended reason.

## Failure Modes

- Steps without expected result: specify the oracle.
- Environment-dependent flakiness: control state and timing.

## Handoffs

Product Manager resolves policy; engineers provide fixtures; [acceptance-criteria.md](../../Product/Product%20Manager/acceptance-criteria.md) supplies business acceptance.
