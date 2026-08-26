# Secret Management

Context: [Security Engineer](README.md).

## Purpose

Control secret creation, storage, use, rotation, and revocation without disclosure.

## Activate When

A service or workflow uses credentials, tokens, signing keys, or other secrets.

## Do Not Use When

Do not print usable secrets, store them in source, or rotate them without considering consumers.

## Required Context

**Needed:** Secret purpose/owner/consumers, approved store, rotation constraints, and mandate.

**Can be deferred or bounded:** Never retrieve or print values just to inventory them; use references and non-sensitive identifiers.

## Workflow

1. Inventory secret purpose and access without copying values into reports.
2. Choose approved storage and runtime injection with minimal privileges and auditability.
3. Plan rotation across consumers, overlap, revocation, and recovery from partial rollout.
4. Test with non-production credentials where possible and verify old access is removed after successful migration.

## Rotation Sequence

Define new credential issuance, deployment to consumers, coexistence where supported, verification, old credential revocation, and rollback limits. For suspected compromise, balance urgent containment with known dependencies under the incident mandate; do not delay merely to perfect documentation.

## Decision Rules

- If a secret is exposed, treat it as compromised and route authorized revocation or rotation.
- If rotation can interrupt service, coordinate overlap and consumer verification before revocation.

## Output Contract

Secret lifecycle plan or authorized change with least privilege, references, rotation sequence, and verification.

## Quality Gates

- Are secrets absent from code, logs, images, URLs, and artifacts?
- Can access be revoked and ownership identified?
- Old access is actually revoked after intended consumers switch, and no report contains usable credentials.

## Failure Modes

- Masking display but storing raw value: prevent ingestion.
- Rotation without consumer map: verify all users.

## Handoffs

DevOps owns secret infrastructure; application owners update consumers; incident owner handles compromise.
