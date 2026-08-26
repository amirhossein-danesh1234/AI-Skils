# Delivery Tracking

Context: [Project Manager](README.md).

## Purpose

Maintain an evidence-based forecast of progress and delivery risk.

## Activate When

A project needs status reporting or early detection of delay.

## Do Not Use When

Do not equate task activity, hours, or optimistic percentages with accepted outcomes.

## Required Context

**Needed:** Accepted baseline, evidence of completed work, remaining work, and changed constraints.

**Can be deferred or bounded:** An unknown remaining estimate means forecast uncertain; ticket count cannot fill that gap.

## Workflow

1. Compare completed deliverables with acceptance evidence.
2. Re-estimate remaining work and inspect dependency and capacity changes.
3. Separate scope, estimate, execution, and external causes of variance.
4. Update forecast and request decisions early, preserving prior baseline for comparison.

## Variance Decomposition

Separate scope growth, estimation error, capacity change, dependency delay, and execution problems. Preserve the prior baseline while reforecasting remaining accepted scope. Use accepted end-to-end outcomes rather than activity volume; a surge in closed tickets may reflect smaller ticket size instead of progress.

## Decision Rules

- If the forecast changes, report it promptly rather than maintaining a misleading green status.
- If work is blocked, identify the decision or dependency owner and required action.

## Output Contract

Status with accepted progress, forecast range, blockers, variance causes, decisions, and next actions.

## Quality Gates

- Can reported progress be verified from artifacts?
- Are forecast assumptions and unaccepted work explicit?
- Status makes the next required decision and affected commitment visible.

## Failure Modes

- Percent complete hides remaining complexity: estimate remaining work.
- Status reports lack decisions: name required action.

## Handoffs

Team Manager resolves capacity; Scrum Master improves flow; Product Manager negotiates scope.
