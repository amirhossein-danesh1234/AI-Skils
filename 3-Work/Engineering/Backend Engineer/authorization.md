# Authorization

Context: [Backend Engineer](README.md).

## Purpose

Enforce who may perform each action on each resource and tenant.

## Activate When

A backend exposes protected operations or roles and permissions change.

## Do Not Use When

Authentication alone is insufficient; UI visibility is not an authorization control.

## Required Context

**Needed:** Approved actor-action-resource-context policy and all access paths.

**Can be deferred or bounded:** Missing policy permits an assessment and question list, not permissive implementation defaults.

## Workflow

1. Translate approved policy into actor-action-resource-context rules.
2. Inspect every read, write, list, export, background, and administrative path.
3. Enforce checks at trusted server boundaries and scope queries to permitted objects and tenants.
4. Test privilege escalation, cross-tenant identifiers, missing permissions, stale roles, and indirect access paths.

## Permission Contract

Represent permissions as actor + action + resource + context, including tenant and lifecycle state where relevant. A role is a convenient grouping, not a complete rule. Specify default denial, delegation, administrative exceptions, and revocation behavior using approved policy.

Trace authorization through list queries, detail reads, updates, bulk operations, file access, nested resources, search, exports, background jobs, and integrations. A protected detail endpoint does not prevent a list or export from leaking the same data. Check object relationships using trusted server data, not a client-supplied owner field.

Build negative tests with at least the relevant unauthorized and cross-tenant identities, and assert both response and absence of forbidden side effects. For bulk operations, define whether failure is atomic or partial and ensure error reporting does not expose forbidden object details. Review caching and stale-role behavior explicitly.

Record the policy owner and unresolved rules. Do not resolve an ambiguous administrative permission by granting broad access. Consult Security Engineer’s [authorization-security.md](../Security%20Engineer/authorization-security.md) for independent bypass analysis after implementation.

## Authority at Effect Time

Recheck grants and object state at the authoritative mutation boundary when they may change after an earlier read. Test stale role caches, nested identifiers from another tenant, bulk mixed-eligibility inputs, exports, and queued work created before revocation. Make service-identity delegation explicit.

## Decision Rules

- If permission is not explicitly granted under policy, deny rather than infer access from authentication.
- If a bulk operation mixes permitted and forbidden objects, define safe all-or-partial behavior explicitly.

## Output Contract

Authorization model and implementation with deny rules, enforcement points, audit behavior, and negative tests.

## Quality Gates

- Can one tenant or lower-privileged actor affect another’s data?
- Are list filtering and object access consistent, including jobs and exports?
- Negative tests assert both denial and absence of forbidden reads or side effects.

## Failure Modes

- Role name substitutes for exact policy: evaluate action and resource.
- One protected endpoint hides an unprotected alternate path: inventory all entry points.

## Handoffs

Product Manager or policy owner approves rules; Security Engineer challenges bypasses; Database Engineer supports scoped access.
