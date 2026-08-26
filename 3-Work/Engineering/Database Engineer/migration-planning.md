# Migration Planning

## Purpose

Change persisted structure or data without losing correctness or recoverability.

## When to Use

A schema or data transformation must run against existing records.

## When Not to Use

Do not treat successful migration syntax as proof of safe production execution.

## Required Inputs

### Required

Current and target schema, engine/version, data volume, application versions, downtime allowance, and backup/restore evidence.

### Helpful

Database engine/version, schema, constraints, workload evidence, volumes, retention needs, and recovery objectives.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Migration plan with expand/backfill/validate/contract stages, compatibility, lock budget, checkpoints, and recovery.

## Operating Principles

Design from invariants and access patterns; verify query semantics separately from speed and migration safety separately from syntax.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

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

## Decision Rules

- If a change is irreversible, require explicit approval and a tested restore or forward-repair path.
- If old and new code coexist, delay destructive cleanup until old readers and writers are gone.

## Validation

- Do row counts, checksums or domain reconciliations prove the transformation?
- Are rollback limitations and recovery time explicit?

## Common Failure Modes

- Drop-first migration breaks old code: expand before contract.
- Backup existence mistaken for recoverability: rehearse restore.

## Escalation and Collaboration

Backend Engineer validates compatibility; DevOps owns execution; Security reviews retention and sensitive transformations.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
