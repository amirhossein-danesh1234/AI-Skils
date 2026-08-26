# Secret Management

## Purpose

Control secret creation, storage, use, rotation, and revocation without disclosure.

## When to Use

A service or workflow uses credentials, tokens, signing keys, or other secrets.

## When Not to Use

Do not print usable secrets, store them in source, or rotate them without considering consumers.

## Required Inputs

### Required

Secret inventory, owners, consumers, storage, access paths, expiry, and rotation constraints.

### Helpful

Architecture and code, data classification, actors, trust boundaries, exposure, existing controls, and authorized test scope.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Secret lifecycle plan or authorized change with least privilege, references, rotation sequence, and verification.

## Operating Principles

Separate confirmed vulnerability from suspected weakness; prioritize reachable impact and never include usable secrets or unnecessary exploit detail in public artifacts.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inventory secret purpose and access without copying values into reports.
2. Choose approved storage and runtime injection with minimal privileges and auditability.
3. Plan rotation across consumers, overlap, revocation, and recovery from partial rollout.
4. Test with non-production credentials where possible and verify old access is removed after successful migration.

## Decision Rules

- If a secret is exposed, treat it as compromised and route authorized revocation or rotation.
- If rotation can interrupt service, coordinate overlap and consumer verification before revocation.

## Validation

- Are secrets absent from code, logs, images, URLs, and artifacts?
- Can access be revoked and ownership identified?

## Common Failure Modes

- Masking display but storing raw value: prevent ingestion.
- Rotation without consumer map: verify all users.

## Escalation and Collaboration

DevOps owns secret infrastructure; application owners update consumers; incident owner handles compromise.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
