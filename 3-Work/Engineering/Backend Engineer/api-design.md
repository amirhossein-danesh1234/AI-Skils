# API Design

## Purpose

Define an endpoint contract that consumers can use correctly under success and failure.

## When to Use

A service needs a new or changed API operation.

## When Not to Use

API architecture owns system-wide topology; do not choose HTTP shapes without business semantics.

## Required Inputs

### Required

Consumer scenarios, resource ownership, operations, permissions, data schema, and compatibility constraints.

### Helpful

Repository, runtime, business rules, contracts, data model, identity context, failure evidence, and deployment constraints.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Contract with request/response schemas, validation, permissions, errors, pagination, idempotency, limits, and version behavior.

## Operating Principles

Enforce invariants at the authoritative boundary, make retries safe, redact sensitive diagnostics, and verify persisted outcomes rather than status codes alone.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect existing API conventions and actual consumer needs.
2. Define operation semantics, resource identifiers, validation, and authoritative business effects.
3. Specify authentication and object-level authorization, error taxonomy, and privacy-safe responses.
4. Design pagination, concurrency, retries, timeouts, and compatibility; verify examples with consumers.

## Decision Rules

- If a retry may repeat a side effect, define an idempotency contract or prohibit automatic retry.
- If a field or behavior change breaks consumers, version or migrate it explicitly.

## Validation

- Are success and error examples consistent with business rules and permissions?
- Can consumers distinguish validation, conflict, authorization, and transient failure?

## Common Failure Modes

- Status codes replace domain semantics: define actual outcomes.
- Unbounded list endpoints: specify stable pagination and limits.

## Escalation and Collaboration

Frontend Engineer validates usability; Security reviews exposure; Database Engineer checks efficient access and consistency.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
