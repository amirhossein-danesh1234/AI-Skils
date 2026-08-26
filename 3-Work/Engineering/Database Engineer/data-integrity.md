# Data Integrity

## Purpose

Detect and prevent invalid, inconsistent, or orphaned persisted data.

## When to Use

Data quality defects or new invariants threaten trustworthy operations.

## When Not to Use

Do not silently repair records by guessing the intended business state.

## Required Inputs

### Required

Approved invariants, schema, affected records, write paths, and historical context.

### Helpful

Database engine/version, schema, constraints, workload evidence, volumes, retention needs, and recovery objectives.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Integrity assessment with violations, cause, preventive controls, repair proposal, and reconciliation evidence.

## Operating Principles

Design from invariants and access patterns; verify query semantics separately from speed and migration safety separately from syntax.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Translate invariants into explicit checks over keys, relationships, ranges, and lifecycle states.
2. Profile violations read-only and identify affected populations and write paths.
3. Determine whether constraints, transactions, validation, or ownership changes prevent recurrence.
4. Propose reversible or auditable repairs and verify results against independent totals.

## Decision Rules

- If the correct value cannot be inferred reliably, quarantine or request owner adjudication.
- If writes continue during repair, coordinate prevention before backfilling.

## Validation

- Are invalid records resolved without creating new contradictions?
- Can the same defect recur through another entry point?

## Common Failure Modes

- Repair script hides root cause: fix prevention.
- Unknown values overwritten with defaults: preserve uncertainty and provenance.

## Escalation and Collaboration

Product Manager resolves business truth; Backend Engineer fixes write paths; DevOps coordinates safe repair.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
