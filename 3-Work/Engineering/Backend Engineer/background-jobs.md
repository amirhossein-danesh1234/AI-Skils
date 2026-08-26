# Background Jobs

Context: [Backend Engineer](README.md).

## Purpose

Design deferred work that tolerates retries, duplication, and worker failure.

## Activate When

An operation should run asynchronously or needs scheduled processing.

## Do Not Use When

Do not move work to a queue without defining user-visible completion and failure.

## Required Context

**Needed:** Business effect, delivery guarantees, deadline, and worker lifecycle.

**Can be deferred or bounded:** Queue product selection is secondary; operation identity and safe retry semantics are required first.

## Workflow

1. Inspect the user outcome and decide whether asynchronous completion is acceptable.
2. Define a durable job identity, minimal payload, ownership, and state transitions.
3. Make side effects idempotent or reconcilable and bound retries with backoff and expiry.
4. Test worker crash, duplicate delivery, poison input, dependency outage, and partial success.

## Job Identity Versus Business Operation

A delivery attempt ID is not a business-operation ID. Persist the intended operation identity and reuse it across retries that represent the same effect. Do not regenerate a payment or dispatch key on each worker run. Distinct business operations may share a job type or order and still require different keys.

For external side effects, apply the provider-specific payload, retention, replay, and ambiguous-outcome contract in [integration-design.md](integration-design.md). After restoring old local state, pause dispatch until affected operations are reconciled with external history. Test the crash between external success and local acknowledgment; queue acknowledgment alone cannot prove an effect occurred only once.

## Lease and Poison Work

Define worker ownership/lease expiry, visibility timeout, retryability, dead-letter disposition, and how operators distinguish a poisoned input from a transient dependency failure. For ordering-sensitive jobs, reject or reconcile stale events against current authoritative state. A job marked delivered is not proof its business effect completed.

## Decision Rules

- If duplicate execution can move money or corrupt state, establish deduplication before enabling retries.
- If work is obsolete after a deadline, expire it rather than process indefinitely.

## Output Contract

Job contract with idempotency, retries, deadlines, concurrency, dead-letter or recovery path, and observability.

## Quality Gates

- Can operators identify and safely recover stuck or failed jobs?
- Does a crash between side effect and acknowledgment preserve correctness?
- Worker crash and lease expiry cannot create an unbounded duplicate-effect loop.

## Failure Modes

- Exactly-once assumed from a queue: design for duplicates.
- Infinite retries amplify outage: bound attempts and surface failure.

## Handoffs

Database Engineer validates atomicity or outbox needs; DevOps owns queue operation; QA tests failure recovery.
