# Dependency Management

Context: [Project Manager](README.md).

## Purpose

Keep delivery prerequisites owned, visible, and actively resolved.

## Activate When

External or cross-team prerequisites threaten delivery.

## Do Not Use When

Product [dependency-analysis.md](../../Product/Product%20Manager/dependency-analysis.md) identifies product prerequisites; this skill manages commitments and timing.

## Required Context

**Needed:** Provider/consumer, required condition, owner, needed date, and current evidence.

**Can be deferred or bounded:** A promised date without confirmed owner remains uncertain; a fallback may be prepared while confirmation is sought.

## Workflow

1. Verify the required artifact or condition with both provider and consumer.
2. Confirm owners and realistic dates rather than relying on informal promises.
3. Track leading signals of delay and identify critical-path consequences.
4. Negotiate sequencing, decoupling, fallback, or escalation before the dependency blocks work.

## Dependency Acceptance

Define the artifact or condition the consumer can actually use, including access and compatibility. Track leading evidence before the required date, not only a red status after it passes. Escalate an unowned dependency with a decision request, impact, and latest useful response time.

## Decision Rules

- If a dependency has no accountable owner, escalate rather than mark it on track.
- If a fallback preserves the outcome at acceptable cost, prepare it before the deadline.

## Output Contract

Dependency register with provider/consumer, condition, commitment, status, trigger, and fallback.

## Quality Gates

- Are commitments confirmed and completion conditions testable?
- Are circular dependencies and stale dates resolved?
- Provider completion is verified against consumer acceptance rather than a verbal done label.

## Failure Modes

- Dependency list without follow-through: assign trigger and action.
- Provider says done but consumer cannot use it: verify acceptance.

## Handoffs

Architecture evaluates decoupling; Team Manager resolves ownership; sponsor handles cross-team authority conflicts.
