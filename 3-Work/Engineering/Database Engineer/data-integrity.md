# Data Integrity

Context: [Database Engineer](README.md).

## Purpose

Detect and prevent invalid, inconsistent, or orphaned persisted data.

## Activate When

Data quality defects or new invariants threaten trustworthy operations.

## Do Not Use When

Do not silently repair records by guessing the intended business state.

## Required Context

**Needed:** Approved invariant, affected population, write paths, and read-only evidence.

**Can be deferred or bounded:** Repair values require trustworthy provenance; unknown truth can remain quarantined for owner adjudication.

## Workflow

1. Translate invariants into explicit checks over keys, relationships, ranges, and lifecycle states.
2. Profile violations read-only and identify affected populations and write paths.
3. Determine whether constraints, transactions, validation, or ownership changes prevent recurrence.
4. Propose reversible or auditable repairs and verify results against independent totals.

## Repair Ledger

Record violation class, record selection rule, evidence for intended value, proposed correction, and validation query. Install or coordinate recurrence prevention before repairing while writers remain active. Reconcile business totals and relationships, not just the count of updated rows.

## Decision Rules

- If the correct value cannot be inferred reliably, quarantine or request owner adjudication.
- If writes continue during repair, coordinate prevention before backfilling.

## Output Contract

Integrity assessment with violations, cause, preventive controls, repair proposal, and reconciliation evidence.

## Quality Gates

- Are invalid records resolved without creating new contradictions?
- Can the same defect recur through another entry point?
- A repair cannot silently convert an unknown value into an asserted business fact.

## Failure Modes

- Repair script hides root cause: fix prevention.
- Unknown values overwritten with defaults: preserve uncertainty and provenance.

## Handoffs

Product Manager resolves business truth; Backend Engineer fixes write paths; DevOps coordinates safe repair.
