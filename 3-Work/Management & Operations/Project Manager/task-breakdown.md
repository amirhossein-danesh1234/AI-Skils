# Task Breakdown

## Purpose

Decompose a deliverable into executable work without losing the outcome.

## When to Use

A plan is too coarse to estimate, assign, or track.

## When Not to Use

Do not split work into arbitrary tiny tasks or dictate implementation detail beyond evidence.

## Required Inputs

### Required

Deliverable, acceptance, technical approach, dependencies, and team conventions.

### Helpful

Approved scope, acceptance conditions, owners, estimates, calendars, dependencies, capacity, risks, and deadline basis.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Work packages with outputs, owners, estimates, dependencies, and completion checks.

## Operating Principles

Report forecast and evidence, not optimistic status colors; change commitments explicitly when assumptions fail.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Start from the accepted deliverable and identify necessary artifacts or behavior.
2. Split by verifiable outputs and meaningful risk boundaries.
3. Include integration, review, test data, deployment, documentation, and operational handoff where needed.
4. Check coverage and remove duplicate or unnecessary tasks.

## Decision Rules

- If a task has no observable completion condition, refine it.
- If decomposition creates excessive coordination, combine work around a coherent owner.

## Validation

- Do tasks collectively produce the deliverable and nothing unrelated?
- Are hidden integration and validation work represented?

## Common Failure Modes

- Only coding tasks counted: include readiness work.
- Task count mistaken for progress: track accepted outputs.

## Escalation and Collaboration

Implementers validate decomposition; QA supplies verification work; Team Manager confirms ownership.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
