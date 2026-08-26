# Bug Reproduction

## Purpose

Create a minimal, reliable account of a defect and its impact.

## When to Use

A reported failure cannot yet be reproduced or communicated clearly.

## When Not to Use

Do not implement speculative fixes or expose sensitive production data in a bug report.

## Required Inputs

### Required

Reported behavior, expected behavior, version, environment, user state, and available evidence.

### Helpful

Requirements, change diff, architecture, critical journeys, known defects, test environments, and release context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Reproduction with prerequisites, steps, expected/actual results, frequency, impact, and sanitized evidence.

## Operating Principles

Prioritize impact, likelihood, change exposure, and usage; report skipped, blocked, flaky, and failed tests separately.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Verify the report against the current version and capture relevant environment details.
2. Reproduce with original context, then remove unnecessary steps and data.
3. Vary one factor at a time to identify boundary conditions and intermittent triggers.
4. Record reliable reproduction or explicitly state remaining uncertainty and next evidence needed.

## Decision Rules

- If the issue cannot be reproduced, do not call it resolved; preserve evidence and narrow the conditions.
- If expected behavior is disputed, route the requirement question separately from the technical symptom.

## Validation

- Can another person reproduce from a clean relevant state?
- Are logs, screenshots, and identifiers sanitized but useful?

## Common Failure Modes

- Vague “does not work”: state the observed difference.
- Reproduction depends on hidden state: document or isolate it.

## Escalation and Collaboration

Product Manager confirms expected behavior; engineers investigate cause; Security handles sensitive exposure.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
