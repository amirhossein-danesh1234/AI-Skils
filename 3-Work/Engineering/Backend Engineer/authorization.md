# Authorization

## Purpose

Enforce who may perform each action on each resource and tenant.

## When to Use

A backend exposes protected operations or roles and permissions change.

## When Not to Use

Authentication alone is insufficient; UI visibility is not an authorization control.

## Required Inputs

### Required

Actor identities, permissions policy, resource ownership, tenant boundaries, and operation inventory.

### Helpful

Repository, runtime, business rules, contracts, data model, identity context, failure evidence, and deployment constraints.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Authorization model and implementation with deny rules, enforcement points, audit behavior, and negative tests.

## Operating Principles

Enforce invariants at the authoritative boundary, make retries safe, redact sensitive diagnostics, and verify persisted outcomes rather than status codes alone.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Translate approved policy into actor-action-resource-context rules.
2. Inspect every read, write, list, export, background, and administrative path.
3. Enforce checks at trusted server boundaries and scope queries to permitted objects and tenants.
4. Test privilege escalation, cross-tenant identifiers, missing permissions, stale roles, and indirect access paths.

## Permission Contract

Represent permissions as actor + action + resource + context, including tenant and lifecycle state where relevant. A role is a convenient grouping, not a complete rule. Specify default denial, delegation, administrative exceptions, and revocation behavior using approved policy.

Trace authorization through list queries, detail reads, updates, bulk operations, file access, nested resources, search, exports, background jobs, and integrations. A protected detail endpoint does not prevent a list or export from leaking the same data. Check object relationships using trusted server data, not a client-supplied owner field.

Build negative tests with at least the relevant unauthorized and cross-tenant identities, and assert both response and absence of forbidden side effects. For bulk operations, define whether failure is atomic or partial and ensure error reporting does not expose forbidden object details. Review caching and stale-role behavior explicitly.

Record the policy owner and unresolved rules. Do not resolve an ambiguous administrative permission by granting broad access. Consult Security Engineer’s authorization-security.md for independent bypass analysis after implementation.

## Decision Rules

- If permission is not explicitly granted under policy, deny rather than infer access from authentication.
- If a bulk operation mixes permitted and forbidden objects, define safe all-or-partial behavior explicitly.

## Validation

- Can one tenant or lower-privileged actor affect another’s data?
- Are list filtering and object access consistent, including jobs and exports?

## Common Failure Modes

- Role name substitutes for exact policy: evaluate action and resource.
- One protected endpoint hides an unprotected alternate path: inventory all entry points.

## Escalation and Collaboration

Product Manager or policy owner approves rules; Security Engineer challenges bypasses; Database Engineer supports scoped access.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
