# CRM Process

## Purpose

Make customer and opportunity records reliable enough for action and handoff.

## When to Use

CRM data is inconsistent, stale, duplicated, or burdensome.

## When Not to Use

Do not collect every possible field or use CRM activity as a proxy for employee value.

## Required Inputs

### Required

Sales process, required decisions, existing fields, ownership, data sources, and privacy constraints.

### Helpful

Customer context, offer, qualification evidence, stage definitions, pricing authority, pipeline data, and delivery constraints.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

CRM rules with fields, stages, validation, ownership, deduplication, retention, and hygiene cadence.

## Operating Principles

Optimize mutual fit, evidence-based stage progression, and sustainable deal economics rather than activity volume.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect which decisions and handoffs depend on CRM data.
2. Define minimum required fields and evidence for each stage.
3. Assign update ownership and rules for duplicates, stale records, and lost opportunities.
4. Test a real handoff and report whether the record supports the next action.

## Decision Rules

- If a field has no decision or compliance purpose, remove it from required collection.
- If automation changes stages, verify evidence and provide correction paths.

## Validation

- Can pipeline reports be reconciled to source records?
- Are permissions and personal-data retention appropriate?

## Common Failure Modes

- Mandatory fields invite fabricated data: require only useful facts.
- Duplicate contacts split history: define identity resolution.

## Escalation and Collaboration

Sales process owns stage meaning; Operations manages recurring hygiene; Security reviews sensitive data access.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
