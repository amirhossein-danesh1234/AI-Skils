# Unit Test Planning

Context: [QA-Test Engineer](README.md).

## Purpose

Select isolated tests for domain rules and local behavior.

## Activate When

A code change needs fast regression confidence at the unit boundary.

## Do Not Use When

Do not mock away the behavior under test or assert private implementation details.

## Required Context

**Needed:** Unit public contract, invariants, dependencies, and existing test conventions.

**Can be deferred or bounded:** If behavior depends on database isolation or protocol semantics, move that proof to integration testing.

## Workflow

1. Inspect the unit’s responsibility and separate pure behavior from external effects.
2. Choose representative normal, boundary, and invalid cases from the contract.
3. Use real lightweight dependencies where practical and mock only genuine external boundaries.
4. Verify tests fail for a plausible defect and remain independent of execution order.

## Independent Oracle

Hand-calculate expected outcomes or derive them from an independent rule, not the implementation formula copied into a test. Test meaningful boundaries and invalid transitions. A mock should isolate an external dependency, not remove the behavior whose correctness the test claims to establish.

## Decision Rules

- If correctness depends on database or protocol semantics, add an integration test rather than over-mocking.
- If a test only repeats implementation logic, replace it with an independent expected result.

## Output Contract

Unit test plan or cases covering meaningful inputs, outputs, errors, and state transitions.

## Quality Gates

- Are tests deterministic and focused on public behavior?
- Would a meaningful regression be detected without brittle coupling?
- Tests detect a plausible mutation while remaining independent of private implementation structure.

## Failure Modes

- Mock call count mistaken for behavior: assert outcomes.
- One test per line: focus on invariant coverage.

## Handoffs

Implementation owner provides seams; [integration-test-planning.md](integration-test-planning.md) covers real boundaries.
