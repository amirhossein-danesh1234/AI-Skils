# Backup Recovery

## Purpose

Prove that required data and service state can be recovered within agreed objectives.

## When to Use

A system needs backup design or recoverability evidence.

## When Not to Use

A successful backup job is not proof of successful restoration.

## Required Inputs

### Required

Data inventory, consistency needs, recovery point/time objectives, dependencies, and authorized test environment.

### Helpful

Actual infrastructure and listeners, release process, identities, dependencies, service objectives, secrets handling, and current incident state.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Backup and restore plan with retention, encryption, access, consistency, rehearsal results, and gaps.

## Operating Principles

Inspect before mutation; use immutable or traceable releases, least privilege, explicit stop conditions, and real service checks.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Identify all state needed for recovery, including configuration and key dependencies.
2. Choose backup frequency and method against acceptable data loss and recovery time.
3. Protect copies from shared failure, accidental deletion, and unauthorized access.
4. Restore into an isolated environment with worker dispatch and live external effects disabled or sandboxed; verify data integrity and a representative safe application operation before any authorized resumption.

## Restore Evidence Contract

Record the backup identity and recovery point, restore target, encryption-key access method, dependency versions, start/end time, validation results, and remaining gaps. Use a clearly isolated target; restoring over live state requires explicit authority and a separate impact plan.

Validate more than file readability: check database consistency, required configuration, object storage or attachment references, identity dependencies, and a representative application operation. Compare recovered counts or domain totals with the expected point in time. If exact reconciliation is impossible, explain the uncertainty and its business effect.

Test loss of the primary environment and access path where feasible. Recovery that requires a credential stored only on the failed host is not independent. Include retention, deletion protection, access review, and periodic rehearsal appropriate to data criticality. The business owner sets acceptable recovery point and time; the engineer reports measured capability, not invented targets.

## External Effects and Replay After Recovery

For systems that dispatch payments, messages, shipments, or other external effects, isolate outbound network paths and credentials as well as the restore database. Disable or sandbox workers, schedulers, webhooks, and notifications before starting restored application processes. Confirm the isolation with harmless checks; do not use a real charge or customer message as the smoke test.

Restoring local state does not reverse effects already accepted by another system. Preserve or reconstruct durable operation identities, then reconcile restored pending jobs, outbox entries, and business records with authoritative external history before authorized replay. Specify which operations are safe to resume, which remain ambiguous, and who can adjudicate them. Do not generate new payment or dispatch identities merely because the restored state predates success. This is a conditional recovery control, not a requirement for every service to adopt an outbox.

Record evidence that the rehearsal caused no live external effects and that the resumption gate distinguishes local consistency from cross-system reconciliation.

## Decision Rules

- If decryption keys share the same failure domain as backups, design independent recovery access.
- If restore exceeds the target, change the recovery design rather than report backup success.

## Validation

- Are measured recovery time and recovered point recorded?
- Do restored data and application behavior reconcile with the intended state?
- For systems with external side effects, were outbound effects contained and restored operations reconciled before replay was authorized?

## Common Failure Modes

- Backup files exist but are unusable: rehearse restore.
- Restore overwrites live data: use explicit isolated targets and approval.

## Escalation and Collaboration

Database Engineer validates consistency; Security checks access and encryption; service owner approves recovery objectives.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
