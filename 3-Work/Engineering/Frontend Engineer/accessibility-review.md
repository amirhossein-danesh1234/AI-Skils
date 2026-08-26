# Accessibility Review

## Purpose

Evaluate whether people using different input and assistive methods can complete the interface.

## When to Use

An interface or change needs accessibility assessment.

## When Not to Use

Automated scans alone cannot establish conformance or practical task accessibility.

## Required Inputs

### Required

Scope, accessibility target, routes and states, supported platforms, and testing access.

### Helpful

Repository instructions, approved UI and behavior, runtime versions, API contracts, existing tests, and supported devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Findings with affected users, reproduction, criterion where applicable, severity, remedy, and test limitations.

## Operating Principles

Follow existing conventions, keep state minimal, test realistic interactions, and distinguish compilation from verified user behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect semantic structure, names, labels, relationships, and status announcements.
2. Walk critical tasks with keyboard, focus navigation, zoom, and relevant assistive technology.
3. Check contrast, non-color cues, target behavior, errors, and dynamic updates against the chosen standard.
4. Combine automated findings with manual evidence and retest fixes in context.

## Decision Rules

- If a control is visually clickable but lacks semantics or keyboard operation, treat it as a functional barrier.
- If testing covers only part of the product, do not claim whole-product conformance.

## Validation

- Can tasks complete without pointer-only actions and without lost focus?
- Are labels, errors, and updates understandable to assistive technology?

## Common Failure Modes

- Scan score treated as certification: disclose manual coverage.
- ARIA added instead of native semantics: prefer correct native controls.

## Escalation and Collaboration

UX and UI resolve behavior and visual barriers; use current W3C WCAG guidance for criterion interpretation.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
