# UX Audit

## Purpose

Identify systemic usability risks across an existing product experience.

## When to Use

A product needs a structured review across journeys, patterns, and accessibility concerns.

## When Not to Use

Use usability-analysis.md for observed task testing and ui-review.md for visual consistency.

## Required Inputs

### Required

Product access, priority journeys, user evidence, design constraints, and review scope.

### Helpful

User tasks, research evidence, current screens and flows, constraints, accessibility needs, and business rules.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Audit with journey coverage, reproducible findings, severity, evidence type, remediation themes, and limitations.

## Operating Principles

Separate observed behavior from interpretation. Optimize comprehension and task completion, not screen count or visual novelty.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inventory priority tasks and review representative states across their full paths.
2. Assess comprehension, discoverability, error prevention, consistency, accessibility, and recovery.
3. Identify recurring root patterns rather than reporting the same issue on every screen.
4. Prioritize by user harm, reach, and confidence; separate quick corrections from structural redesign.

## Decision Rules

- If evidence is heuristic, label it as a hypothesis rather than measured user failure.
- If the audit cannot access key roles or devices, list the unreviewed coverage.

## Validation

- Are findings reproducible and tied to task consequences?
- Do remediation themes avoid conflicting local fixes?

## Common Failure Modes

- Long checklist without prioritization: rank by task impact.
- Audit becomes redesign without mandate: separate recommendations from implementation.

## Escalation and Collaboration

UI and Frontend specialists assess visual and accessibility implementation; Product Manager owns prioritization.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
