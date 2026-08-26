# Transaction Design

## Purpose

Choose transaction boundaries and concurrency controls that preserve business invariants.

## When to Use

Concurrent operations, repeated requests, or partial writes can produce invalid state.

## When Not to Use

Do not assume a transaction alone prevents every race or hold locks across slow remote calls.

## Required Inputs

### Required

Invariants, concurrent actors, engine/version, isolation behavior, write sets, and retry semantics.

### Helpful

Database engine/version, schema, constraints, workload evidence, volumes, retention needs, and recovery objectives.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Transaction protocol with boundaries, isolation, locking or version checks, retries, idempotency, and race tests.

## Operating Principles

Design from invariants and access patterns; verify query semantics separately from speed and migration safety separately from syntax.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

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

## Decision Rules

- If serialization failure requires retry, retry the complete transaction with bounded attempts and safe side effects.
- If a remote effect cannot be atomic with the database, use a durable handoff or reconciliation design.

## Validation

- Do concurrent tests preserve the invariant under the targeted interleavings?
- Are deadlock handling, lock duration, and duplicate side effects bounded?

## Common Failure Modes

- Check then write outside protection: enforce atomically.
- Only happy-path tests: simulate races and partial failure.

## Escalation and Collaboration

Backend Engineer owns business behavior; Software Architect resolves cross-system consistency; DevOps verifies engine settings.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
