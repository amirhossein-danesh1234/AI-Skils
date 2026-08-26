# Architecture Decision Record

## Purpose

Record a consequential technical choice and the conditions behind it.

## When to Use

A structural decision needs durable context for future maintainers.

## When Not to Use

Do not use an ADR as a design tutorial or retroactively invent unanimous approval.

## Required Inputs

### Required

Decision question, constraints, alternatives, evidence, participants, and actual approval status.

### Helpful

Current topology and code, domain rules, load evidence, quality targets, team capabilities, constraints, and migration context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

ADR with context, options, decision, consequences, status, owner, date, and revisit triggers.

## Operating Principles

Prefer a modular single deployment when adequate. Introduce distribution or abstraction only for demonstrated needs, with observable failure and recovery behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect existing ADR conventions and related decisions.
2. State the problem and constraints at the time of choice.
3. Summarize credible alternatives and why they were rejected.
4. Record the chosen option, trade-offs, unresolved risks, and supersession or review conditions.

## Decision Rules

- If the decision is proposed, label it proposed rather than accepted.
- If context materially changes, supersede the record instead of erasing history.

## Validation

- Could a future engineer understand why the choice was reasonable?
- Are links, evidence, status, and consequences accurate?

## Common Failure Modes

- Decision without alternatives: preserve the trade-off.
- Revision rewrites history: add a new status or superseding record.

## Escalation and Collaboration

Relevant engineering owners review consequences; decision authority confirms acceptance.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
