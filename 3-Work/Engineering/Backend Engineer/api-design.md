# API Design

Context: [Backend Engineer](README.md).

## Purpose

Define an endpoint contract that consumers can use correctly under success and failure.

## Activate When

A service needs a new or changed API operation.

## Do Not Use When

API architecture owns system-wide topology; do not choose HTTP shapes without business semantics.

## Required Context

**Needed:** Consumer scenario, operation effect, resource ownership, and permission policy.

**Can be deferred or bounded:** Transport details can follow semantics; unresolved consequential rules block affected endpoints, not unrelated contract work.

## Workflow

1. Inspect existing API conventions and actual consumer needs.
2. Define operation semantics, resource identifiers, validation, and authoritative business effects.
3. Specify authentication and object-level authorization, error taxonomy, and privacy-safe responses.
4. Design pagination, concurrency, retries, timeouts, and compatibility; verify examples with consumers.

## Contract Examples

Specify request and response examples for success, invalid input, denied access, conflict, transient failure, and unknown external outcome. For list operations define deterministic ordering and pagination stability. A compatibility test must exercise a representative existing consumer, not merely validate the new schema.

## Decision Rules

- If a retry may repeat a side effect, define an idempotency contract or prohibit automatic retry.
- If a field or behavior change breaks consumers, version or migrate it explicitly.

## Output Contract

Contract with request/response schemas, validation, permissions, errors, pagination, idempotency, limits, and version behavior.

## Quality Gates

- Are success and error examples consistent with business rules and permissions?
- Can consumers distinguish validation, conflict, authorization, and transient failure?
- Equivalent retries and concurrent updates have an explicit contract rather than accidental framework behavior.

## Failure Modes

- Status codes replace domain semantics: define actual outcomes.
- Unbounded list endpoints: specify stable pagination and limits.

## Handoffs

Frontend Engineer validates usability; Security reviews exposure; Database Engineer checks efficient access and consistency.
