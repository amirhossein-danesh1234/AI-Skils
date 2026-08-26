# Integration Test Planning

Context: [QA-Test Engineer](README.md).

## Purpose

Verify that real components agree on contracts, persistence, and failure behavior.

## Activate When

A change crosses database, service, queue, or external-adapter boundaries.

## Do Not Use When

Do not call a fully mocked boundary an integration test.

## Required Context

**Needed:** Boundary contract, dependency semantics/version, fixtures, and failure modes.

**Can be deferred or bounded:** If a substitute lacks production semantics, label the gap and add the actual engine for that risk.

## Workflow

1. Identify assumptions that unit tests cannot validate across the boundary.
2. Use an appropriate real dependency or contract-faithful controlled substitute and state fidelity limits.
3. Test serialization, transactions, permissions, retries, ordering, and error mapping.
4. Verify authoritative state after operations and isolate test data.

## Boundary Fidelity

Identify the assumption crossing the boundary: serialization, transaction, ordering, permission, retry, or error mapping. Assert both the response and persisted/downstream effect. Test partial completion and cleanup failure; a fully mocked call cannot establish the real boundary guarantee.

## Decision Rules

- If production uses a database feature absent in the test substitute, use the relevant engine for that check.
- If external calls incur side effects or cost, use an authorized sandbox or deterministic adapter test.

## Output Contract

Integration plan or tests with setup, contract assertions, persistence checks, cleanup, and failure injection.

## Quality Gates

- Do tests verify both response and persisted or downstream effects?
- Are isolation, cleanup, and version compatibility controlled?
- Environment fidelity matches the specific behavior claimed by the test.

## Failure Modes

- Different engine hides behavior: disclose or fix fidelity.
- Happy-path integration only: exercise partial failure.

## Handoffs

Backend and Database Engineers define contracts; DevOps supplies isolated dependencies; Security reviews sensitive test data.
