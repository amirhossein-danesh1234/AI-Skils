# Background Jobs

## Purpose

Design deferred work that tolerates retries, duplication, and worker failure.

## When to Use

An operation should run asynchronously or needs scheduled processing.

## When Not to Use

Do not move work to a queue without defining user-visible completion and failure.

## Required Inputs

### Required

Job purpose, trigger, payload, side effects, timing, dependencies, and delivery guarantees.

### Helpful

Repository, runtime, business rules, contracts, data model, identity context, failure evidence, and deployment constraints.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Job contract with idempotency, retries, deadlines, concurrency, dead-letter or recovery path, and observability.

## Operating Principles

Enforce invariants at the authoritative boundary, make retries safe, redact sensitive diagnostics, and verify persisted outcomes rather than status codes alone.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect the user outcome and decide whether asynchronous completion is acceptable.
2. Define a durable job identity, minimal payload, ownership, and state transitions.
3. Make side effects idempotent or reconcilable and bound retries with backoff and expiry.
4. Test worker crash, duplicate delivery, poison input, dependency outage, and partial success.

## Job Identity Versus Business Operation

A delivery attempt ID is not a business-operation ID. Persist the intended operation identity and reuse it across retries that represent the same effect. Do not regenerate a payment or dispatch key on each worker run. Distinct business operations may share a job type or order and still require different keys.

For external side effects, apply the provider-specific payload, retention, replay, and ambiguous-outcome contract in [integration-design.md](integration-design.md). After restoring old local state, pause dispatch until affected operations are reconciled with external history. Test the crash between external success and local acknowledgment; queue acknowledgment alone cannot prove an effect occurred only once.

## Decision Rules

- If duplicate execution can move money or corrupt state, establish deduplication before enabling retries.
- If work is obsolete after a deadline, expire it rather than process indefinitely.

## Validation

- Can operators identify and safely recover stuck or failed jobs?
- Does a crash between side effect and acknowledgment preserve correctness?

## Common Failure Modes

- Exactly-once assumed from a queue: design for duplicates.
- Infinite retries amplify outage: bound attempts and surface failure.

## Escalation and Collaboration

Database Engineer validates atomicity or outbox needs; DevOps owns queue operation; QA tests failure recovery.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
