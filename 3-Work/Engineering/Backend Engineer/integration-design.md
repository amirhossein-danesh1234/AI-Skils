# Integration Design

## Purpose

Connect external systems while containing contract, trust, and partial-failure risks.

## When to Use

A service needs a third-party API, webhook, or cross-system exchange.

## When Not to Use

Do not assume external success, availability, or schema stability.

## Required Inputs

### Required

Provider contract/version, auth, payloads, business effects, rate limits, and failure tolerance.

### Helpful

Repository, runtime, business rules, contracts, data model, identity context, failure evidence, and deployment constraints.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Integration boundary with mapping, validation, timeouts, retries, idempotency, reconciliation, and monitoring.

## Operating Principles

Enforce invariants at the authoritative boundary, make retries safe, redact sensitive diagnostics, and verify persisted outcomes rather than status codes alone.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect official provider behavior and test credentials in an authorized environment.
2. Map identifiers, units, time zones, schema versions, and ownership explicitly.
3. Define timeout and retry budgets, webhook verification, deduplication, and ordering treatment.
4. Test provider errors, malformed payloads, delayed callbacks, and ambiguous outcomes; design reconciliation.

## Idempotency Contract for External Effects

For money movement or another non-idempotent external effect, distinguish the semantic business operation from a network attempt, worker delivery, and incoming event. Persist an operation identity before dispatch and reuse its provider key for retries of that same intended operation. Different legitimate actions may need distinct identities even when they share an order or customer.

Define tenant/account and action scope, key uniqueness, payload binding, mismatch behavior, concurrent replay, result persistence, and retention or expiry. Verify the provider's actual contract for the endpoint and version; do not assume a universal key lifetime or that every failure is cached. Preserve a mapping between internal operation, provider request key, and authoritative result.

When a response is lost after external success, use a guaranteed safe replay of the same key or an authoritative status/reconciliation path. If the key expired or guarantees are insufficient, stop automatic redispatch and resolve the unknown state. A new key can create a second effect. Incoming webhook deduplication is separate from operation-level idempotency and must survive worker crashes and out-of-order events.

Test crash-after-external-success, concurrent attempts, changed payload under the same key, duplicate events, and retry after the provider retention boundary with a contract-faithful safe environment. [Stripe's idempotency documentation](https://docs.stripe.com/api/idempotent_requests) illustrates why provider-specific retention and request semantics must be inspected; apply the actual provider's rules, not Stripe assumptions to another service.

## Decision Rules

- If a timeout leaves outcome unknown, preserve the semantic operation identity. Use same-key replay only under verified provider guarantees, or query/reconcile authoritative status; do not create a fresh identity to escape ambiguity.
- If provider data is untrusted, validate it before business processing or storage.

## Validation

- Can both systems converge after partial failure?
- Are rate limits, token handling, and contract changes observable?

## Common Failure Modes

- Happy-path SDK call treated as integration: test failures.
- Webhook delivery trusted blindly: verify authenticity and replay policy.

## Escalation and Collaboration

Security reviews trust; Database Engineer checks consistency; DevOps handles operational signals; Product Manager defines degraded behavior.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
