# Transaction Design

Context: [Database Engineer](README.md).

## Purpose

Choose transaction boundaries and concurrency controls that preserve business invariants.

## Activate When

Concurrent operations, repeated requests, or partial writes can produce invalid state.

## Do Not Use When

Do not assume a transaction alone prevents every race or hold locks across slow remote calls.

## Required Context

**Needed:** Invariant, conflicting writers, engine semantics, and side-effect boundaries.

**Can be deferred or bounded:** Choose a mechanism after constructing the race; stronger isolation is not automatically the cheapest correct control.

## Workflow

1. Identify the invariant and construct an interleaving that could violate it.
2. Inspect actual engine isolation semantics and constraint capabilities.
3. Choose atomic updates, uniqueness, row locks, optimistic versions, or stronger isolation to address the specific race.
4. Define whole-transaction retry and external side-effect coordination; test competing schedules and crash points.

## Concurrency Proof Sketch

Write a concrete conflicting schedule before choosing a mechanism: transaction A reads a value, transaction B reads the same value, then both attempt writes that would violate an invariant. Specify what outcome is allowed, what must be rejected, and which database operation enforces that result.

Choose the narrowest correct protection. An atomic conditional update may protect a single-row transition; uniqueness may prevent duplicate creation; explicit locking may serialize access to known rows; optimistic version checks may detect lost updates; stronger isolation may be needed for broader predicates. Verify the actual engine semantics and failure codes rather than assuming the names of isolation levels mean identical behavior everywhere.

For retries, bound attempts and elapsed time, use backoff where appropriate, and rerun the complete transaction when required by the engine. Do not repeat external side effects that occurred before a transaction failed. For cross-system effects, consider a durable outbox, idempotent consumer, status query, or reconciliation protocol according to the actual architecture.

Test with controlled interleavings, not just many simultaneous requests and hope. Record the invariant before and after, conflict outcome, retry behavior, and any deadlock or starvation risk. Review lock ordering and duration. Long remote calls inside database transactions require explicit justification and failure analysis.

Reference for one engine’s semantics: [PostgreSQL transaction isolation](https://www.postgresql.org/docs/current/transaction-iso.html). Resolve the documentation to the installed version before applying details.

## Controlled Interleavings

Use barriers or explicit schedules to force the violating read/write order. Check both successful and rejected outcomes, deadlock/serialization retries, and lock ordering. For predicate invariants, test rows that do not yet exist; locking a current row may not protect a future insertion.

## Decision Rules

- If serialization failure requires retry, retry the complete transaction with bounded attempts and safe side effects.
- If a remote effect cannot be atomic with the database, use a durable handoff or reconciliation design.

## Output Contract

Transaction protocol with boundaries, isolation, locking or version checks, retries, idempotency, and race tests.

## Quality Gates

- Do concurrent tests preserve the invariant under the targeted interleavings?
- Are deadlock handling, lock duration, and duplicate side effects bounded?
- The selected protection addresses the demonstrated race and retries do not repeat external effects.

## Failure Modes

- Check then write outside protection: enforce atomically.
- Only happy-path tests: simulate races and partial failure.

## Handoffs

Backend Engineer owns business behavior; Software Architect resolves cross-system consistency; DevOps verifies engine settings.
