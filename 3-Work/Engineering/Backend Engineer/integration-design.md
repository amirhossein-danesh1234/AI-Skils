# Integration Design

Context: [Backend Engineer](README.md).

## Purpose

Connect external systems while containing contract, trust, and partial-failure risks.

## Activate When

A service needs a third-party API, webhook, or cross-system exchange.

## Do Not Use When

Do not assume external success, availability, or schema stability.

## Required Context

**Needed:** Actual provider contract/version, intended effects, trust, and failure tolerance.

**Can be deferred or bounded:** A design can use a sandbox; live credentials or external effects require explicit authority.

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

## Webhook and Reconciliation

Verify webhook authenticity using the provider mechanism and raw payload requirements; distinguish authenticity from business validity and replay protection. Reconcile out-of-order events against authoritative status rather than trusting arrival order. Bound provider rate-limit retries and retain unresolved operations for an owned repair path.

## Decision Rules

- If a timeout leaves outcome unknown, preserve the semantic operation identity. Use same-key replay only under verified provider guarantees, or query/reconcile authoritative status; do not create a fresh identity to escape ambiguity.
- If provider data is untrusted, validate it before business processing or storage.

## Output Contract

Integration boundary with mapping, validation, timeouts, retries, idempotency, reconciliation, and monitoring.

## Quality Gates

- Can both systems converge after partial failure?
- Are rate limits, token handling, and contract changes observable?
- Lost response, duplicate callback, changed payload, and expired idempotency protection have distinct safe behavior.

## Failure Modes

- Happy-path SDK call treated as integration: test failures.
- Webhook delivery trusted blindly: verify authenticity and replay policy.

## Handoffs

Security reviews trust; Database Engineer checks consistency; DevOps handles operational signals; Product Manager defines degraded behavior.
