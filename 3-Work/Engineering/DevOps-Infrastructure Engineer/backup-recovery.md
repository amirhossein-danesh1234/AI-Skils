# Backup Recovery

Context: [DevOps-Infrastructure Engineer](README.md).

## Purpose

Prove that required data and service state can be recovered within agreed objectives.

## Activate When

A system needs backup design or recoverability evidence.

## Do Not Use When

A successful backup job is not proof of successful restoration.

## Required Context

**Needed:** Recovery state inventory, recovery objectives, backup identity, and isolated test target.

**Can be deferred or bounded:** Without owner-set objectives, report measured capability only; no destructive restore on a guessed target.

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

## Recovery Dependency Order

Restore required keys/configuration and compatible services in dependency order. Validate domain totals at the selected recovery point, then test the real operation with outbound effects contained. Document when credentials, external status, or attachments are not covered by the backup and how that limits recovery.

## Decision Rules

- If decryption keys share the same failure domain as backups, design independent recovery access.
- If restore exceeds the target, change the recovery design rather than report backup success.

## Output Contract

Backup and restore plan with retention, encryption, access, consistency, rehearsal results, and gaps.

## Quality Gates

- Are measured recovery time and recovered point recorded?
- Do restored data and application behavior reconcile with the intended state?
- For systems with external side effects, were outbound effects contained and restored operations reconciled before replay was authorized?
- The drill proves usable recovery and no live side effects, not merely successful extraction of files.

## Failure Modes

- Backup files exist but are unusable: rehearse restore.
- Restore overwrites live data: use explicit isolated targets and approval.

## Handoffs

Database Engineer validates consistency; Security checks access and encryption; service owner approves recovery objectives.
