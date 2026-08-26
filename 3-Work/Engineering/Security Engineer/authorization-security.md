# Authorization Security

Context: [Security Engineer](README.md).

## Purpose

Find permission bypasses across objects, actions, tenants, and administrative paths.

## Activate When

A permissions model or protected operation requires adversarial review.

## Do Not Use When

Do not infer authorization correctness from login success or hidden UI controls.

## Required Context

**Needed:** Approved policy, all access paths, tenants, and bounded test actors.

**Can be deferred or bounded:** An incomplete policy permits a coverage-gap report; it does not justify granting a broad admin role.

## Workflow

1. Model actor-action-resource-context combinations from approved policy.
2. Inspect direct, list, bulk, export, nested, background, and administrative access paths.
3. Test horizontal and vertical escalation, tenant substitution, stale grants, and indirect object references.
4. Verify deny behavior, audit usefulness, and consistency across equivalent operations.

## Bypass Matrix

Test the same protected object through detail, list, export, nested resource, bulk operation, file URL, cache, job, and integration where present. Change tenant, owner, lifecycle, and grant timing independently. Assert absence of effects and data leakage, not only a denial status.

## Decision Rules

- If access is inferred from a client-supplied owner or tenant identifier, require trusted server-side scoping.
- If a permission service is unavailable, define a fail-safe behavior appropriate to the operation.

## Output Contract

Permission coverage matrix, bypass findings, enforcement requirements, and negative regression cases.

## Quality Gates

- Can an actor obtain data or effects outside their grant through any alternate path?
- Are policy changes and revocations reflected as intended?
- Equivalent paths enforce consistent grants, including after revocation or context changes.

## Failure Modes

- Endpoint-only matrix misses object scope: test data-level rules.
- Admin role treated as unlimited: validate exact administrative authority.

## Handoffs

Backend Engineer owns enforcement; policy owner resolves ambiguity; QA automates negative cases.
