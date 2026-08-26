# Authorization Security

## Purpose

Find permission bypasses across objects, actions, tenants, and administrative paths.

## When to Use

A permissions model or protected operation requires adversarial review.

## When Not to Use

Do not infer authorization correctness from login success or hidden UI controls.

## Required Inputs

### Required

Approved policy, roles, tenant model, endpoints/jobs, object relationships, and authorized test identities.

### Helpful

Architecture and code, data classification, actors, trust boundaries, exposure, existing controls, and authorized test scope.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Permission coverage matrix, bypass findings, enforcement requirements, and negative regression cases.

## Operating Principles

Separate confirmed vulnerability from suspected weakness; prioritize reachable impact and never include usable secrets or unnecessary exploit detail in public artifacts.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Model actor-action-resource-context combinations from approved policy.
2. Inspect direct, list, bulk, export, nested, background, and administrative access paths.
3. Test horizontal and vertical escalation, tenant substitution, stale grants, and indirect object references.
4. Verify deny behavior, audit usefulness, and consistency across equivalent operations.

## Decision Rules

- If access is inferred from a client-supplied owner or tenant identifier, require trusted server-side scoping.
- If a permission service is unavailable, define a fail-safe behavior appropriate to the operation.

## Validation

- Can an actor obtain data or effects outside their grant through any alternate path?
- Are policy changes and revocations reflected as intended?

## Common Failure Modes

- Endpoint-only matrix misses object scope: test data-level rules.
- Admin role treated as unlimited: validate exact administrative authority.

## Escalation and Collaboration

Backend Engineer owns enforcement; policy owner resolves ambiguity; QA automates negative cases.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
