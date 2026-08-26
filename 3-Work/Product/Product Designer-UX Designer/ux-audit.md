# UX Audit

Context: [Product Designer-UX Designer](README.md).

## Purpose

Identify systemic usability risks across an existing product experience.

## Activate When

A product needs a structured review across journeys, patterns, and accessibility concerns.

## Do Not Use When

Use [usability-analysis.md](usability-analysis.md) for observed task testing and [ui-review.md](../UI%20Designer/ui-review.md) for visual consistency.

## Required Context

**Needed:** Review scope, priority journeys, and accessible product states.

**Can be deferred or bounded:** Unavailable roles/devices remain coverage gaps; a partial audit can still report confirmed defects.

## Workflow

1. Inventory priority tasks and review representative states across their full paths.
2. Assess comprehension, discoverability, error prevention, consistency, accessibility, and recovery.
3. Identify recurring root patterns rather than reporting the same issue on every screen.
4. Prioritize by user harm, reach, and confidence; separate quick corrections from structural redesign.

## Systemic Finding

Cluster repeated manifestations under the shared interaction defect, retaining representative locations and affected tasks. Mark heuristic concerns separately from observed task failures. For each high-priority issue, specify a falsifiable retest rather than delivering a full redesign without evidence.

## Decision Rules

- If evidence is heuristic, label it as a hypothesis rather than measured user failure.
- If the audit cannot access key roles or devices, list the unreviewed coverage.

## Output Contract

Audit with journey coverage, reproducible findings, severity, evidence type, remediation themes, and limitations.

## Quality Gates

- Are findings reproducible and tied to task consequences?
- Do remediation themes avoid conflicting local fixes?
- Severity follows task harm and recovery, not the number of screenshots carrying the defect.

## Failure Modes

- Long checklist without prioritization: rank by task impact.
- Audit becomes redesign without mandate: separate recommendations from implementation.

## Handoffs

UI and Frontend specialists assess visual and accessibility implementation; Product Manager owns prioritization.
