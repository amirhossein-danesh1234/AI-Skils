# Dependency Management

## Purpose

Keep delivery prerequisites owned, visible, and actively resolved.

## When to Use

External or cross-team prerequisites threaten delivery.

## When Not to Use

Product dependency-analysis.md identifies product prerequisites; this skill manages commitments and timing.

## Required Inputs

### Required

Dependency map, deliverables, owners, required dates, confidence, and alternatives.

### Helpful

Approved scope, acceptance conditions, owners, estimates, calendars, dependencies, capacity, risks, and deadline basis.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Dependency register with provider/consumer, condition, commitment, status, trigger, and fallback.

## Operating Principles

Report forecast and evidence, not optimistic status colors; change commitments explicitly when assumptions fail.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Verify the required artifact or condition with both provider and consumer.
2. Confirm owners and realistic dates rather than relying on informal promises.
3. Track leading signals of delay and identify critical-path consequences.
4. Negotiate sequencing, decoupling, fallback, or escalation before the dependency blocks work.

## Decision Rules

- If a dependency has no accountable owner, escalate rather than mark it on track.
- If a fallback preserves the outcome at acceptable cost, prepare it before the deadline.

## Validation

- Are commitments confirmed and completion conditions testable?
- Are circular dependencies and stale dates resolved?

## Common Failure Modes

- Dependency list without follow-through: assign trigger and action.
- Provider says done but consumer cannot use it: verify acceptance.

## Escalation and Collaboration

Architecture evaluates decoupling; Team Manager resolves ownership; sponsor handles cross-team authority conflicts.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
