# Funnel Analysis

## Purpose

Locate where an eligible population stops progressing through a defined task.

## When to Use

A multi-step journey has unexplained drop-off.

## When Not to Use

Do not claim the observed drop causes business loss without checking intent and alternative paths.

## Required Inputs

### Required

Event definitions, eligible population, step order, identity, conversion window, and tracking history.

### Helpful

Decision question, event and identity definitions, time windows, source access, instrumentation history, and relevant product changes.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Funnel definition, counts and rates, segment differences, tracking checks, likely mechanisms, and next investigation.

## Operating Principles

Preserve grain and exposure definitions, reconcile counts, and report null or inconclusive findings as readily as positive ones.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Validate event semantics and construct a user or session-level sequence at a declared grain.
2. Define entry eligibility, allowed order, repeated steps, alternative routes, and completion window.
3. Compare counts and conversion across meaningful segments and periods.
4. Investigate large losses with UX evidence and instrumentation checks before recommending changes.

## Decision Rules

- If steps are optional or order varies, model branches rather than forcing one linear funnel.
- If the final window is incomplete, exclude or label immature entries.

## Validation

- Do counts reconcile and denominators remain consistent?
- Can tracking loss or identity fragmentation explain the drop?

## Common Failure Modes

- Page views treated as task intent: qualify entry.
- Different cohorts compared as one path: preserve entity-level progression.

## Escalation and Collaboration

UX Designer investigates friction; Backend and Frontend Engineers validate events; Product Manager prioritizes intervention.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
