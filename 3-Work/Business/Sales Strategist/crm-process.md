# CRM Process

Context: [Sales Strategist](README.md).

## Purpose

Make customer and opportunity records reliable enough for action and handoff.

## Activate When

CRM data is inconsistent, stale, duplicated, or burdensome.

## Do Not Use When

Do not collect every possible field or use CRM activity as a proxy for employee value.

## Required Context

**Needed:** Decisions/handoffs the CRM supports, stage definitions, record owners, and privacy limits.

**Can be deferred or bounded:** Optional fields should not become mandatory merely because the CRM supports them.

## Workflow

1. Inspect which decisions and handoffs depend on CRM data.
2. Define minimum required fields and evidence for each stage.
3. Assign update ownership and rules for duplicates, stale records, and lost opportunities.
4. Test a real handoff and report whether the record supports the next action.

## Record Usability

Test whether a new owner can identify buyer problem, stage evidence, promises, next action, and authority from the record. Define duplicate identity, reopen/closed treatment, aging, and retention. A required field whose answer is genuinely unknown must support unknown rather than encourage fabricated entries.

## Decision Rules

- If a field has no decision or compliance purpose, remove it from required collection.
- If automation changes stages, verify evidence and provide correction paths.

## Output Contract

CRM rules with fields, stages, validation, ownership, deduplication, retention, and hygiene cadence.

## Quality Gates

- Can pipeline reports be reconciled to source records?
- Are permissions and personal-data retention appropriate?
- Pipeline reports reconcile to records with consistent evidence-based stage meanings.

## Failure Modes

- Mandatory fields invite fabricated data: require only useful facts.
- Duplicate contacts split history: define identity resolution.

## Handoffs

Sales process owns stage meaning; Operations manages recurring hygiene; Security reviews sensitive data access.
