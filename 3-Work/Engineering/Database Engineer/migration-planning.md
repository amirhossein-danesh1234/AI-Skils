# Migration Planning

Context: [Database Engineer](README.md).

## Purpose

Change persisted structure or data without losing correctness or recoverability.

## Activate When

A schema or data transformation must run against existing records.

## Do Not Use When

Do not treat successful migration syntax as proof of safe production execution.

## Required Context

**Needed:** Current/target state, data volume, mixed-version behavior, and permitted impact.

**Can be deferred or bounded:** Preliminary design can list missing restore evidence; destructive execution cannot proceed on that omission.

## Workflow

1. Inspect current data for violations that the new schema would reject.
2. Define backward and forward compatibility across mixed application versions.
3. Design bounded, resumable backfills with reconciliation and progress visibility.
4. Rehearse on representative data, measure locks and duration, and define abort and recovery conditions.

## Execution and Recovery Gates

Before execution, identify the exact database, environment, migration revision, affected tables, expected row counts, available disk, replica implications, lock-sensitive operations, and authorized maintenance scope. Preserve a preflight record without exposing sensitive records.

For each stage, state start condition, operation, maximum acceptable impact, progress signal, validation query, and abort action. Backfills should be restartable without duplicating effects and should have a stable way to identify completed work. Throttle against observed service health rather than a guessed universal batch size.

Validate business totals and relationships as well as technical row counts. If data changes while migration runs, define how the final reconciliation closes the gap. Do not drop an old column or table until all relevant readers, writers, jobs, exports, and rollback versions are accounted for.

Separate application rollback, schema rollback, data restoration, and forward repair. State which are possible at each stage and whether they lose new writes. A restore plan needs actual restore evidence and acceptable recovery time; a backup filename alone is insufficient. If the only safe response to a failed destructive stage requires unavailable authority or recovery capability, do not start that stage.

## Cutover Reconciliation

Specify how writes during backfill reach the target representation and how divergence is detected. Separate restartable backfill checkpoints from application cutover. Test an old reader, old writer, new reader, and new writer at the intended coexistence stage, including rollback limitations.

## Decision Rules

- If a change is irreversible, require explicit approval and a tested restore or forward-repair path.
- If old and new code coexist, delay destructive cleanup until old readers and writers are gone.

## Output Contract

Migration plan with expand/backfill/validate/contract stages, compatibility, lock budget, checkpoints, and recovery.

## Quality Gates

- Do row counts, checksums or domain reconciliations prove the transformation?
- Are rollback limitations and recovery time explicit?
- Destructive cleanup waits until all relevant readers/writers and rollback versions no longer require the old representation.

## Failure Modes

- Drop-first migration breaks old code: expand before contract.
- Backup existence mistaken for recoverability: rehearse restore.

## Handoffs

Backend Engineer validates compatibility; DevOps owns execution; Security reviews retention and sensitive transformations.
