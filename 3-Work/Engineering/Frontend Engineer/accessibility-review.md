# Accessibility Review

Context: [Frontend Engineer](README.md).

## Purpose

Evaluate whether people using different input and assistive methods can complete the interface.

## Activate When

An interface or change needs accessibility assessment.

## Do Not Use When

Automated scans alone cannot establish conformance or practical task accessibility.

## Required Context

**Needed:** Target routes/tasks, access to rendered states, and intended standard/platforms.

**Can be deferred or bounded:** A partial manual review is useful without every device, but coverage limits prohibit full conformance claims.

## Workflow

1. Inspect semantic structure, names, labels, relationships, and status announcements.
2. Walk critical tasks with keyboard, focus navigation, zoom, and relevant assistive technology.
3. Check contrast, non-color cues, target behavior, errors, and dynamic updates against the chosen standard.
4. Combine automated findings with manual evidence and retest fixes in context.

## Task Evidence

Record browser/assistive method, starting focus, actions, observed barrier, and affected task. Test modal entry/exit, asynchronous errors, form relationships, zoom/reflow, and status announcements where present. Prefer native semantics; use ARIA only when the behavior and keyboard contract are actually implemented.

## Decision Rules

- If a control is visually clickable but lacks semantics or keyboard operation, treat it as a functional barrier.
- If testing covers only part of the product, do not claim whole-product conformance.

## Output Contract

Findings with affected users, reproduction, criterion where applicable, severity, remedy, and test limitations.

## Quality Gates

- Can tasks complete without pointer-only actions and without lost focus?
- Are labels, errors, and updates understandable to assistive technology?
- A keyboard-only path completes the critical task and retains meaningful focus after state changes.

## Failure Modes

- Scan score treated as certification: disclose manual coverage.
- ARIA added instead of native semantics: prefer correct native controls.

## Handoffs

UX and UI resolve behavior and visual barriers; use current W3C WCAG guidance for criterion interpretation.
