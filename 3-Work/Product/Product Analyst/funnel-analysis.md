# Funnel Analysis

Context: [Product Analyst](README.md).

## Purpose

Locate where an eligible population stops progressing through a defined task.

## Activate When

A multi-step journey has unexplained drop-off.

## Do Not Use When

Do not claim the observed drop causes business loss without checking intent and alternative paths.

## Required Context

**Needed:** Ordered or branched task events, identity, entry eligibility, and completion window.

**Can be deferred or bounded:** Without sequence-level data, report step counts rather than claiming an entity-level funnel.

## Workflow

1. Validate event semantics and construct a user or session-level sequence at a declared grain.
2. Define entry eligibility, allowed order, repeated steps, alternative routes, and completion window.
3. Compare counts and conversion across meaningful segments and periods.
4. Investigate large losses with UX evidence and instrumentation checks before recommending changes.

## Sequence Audit

Manually trace a few completed, abandoned, retried, and alternative-route cases. Reconcile raw events to deduplicated entities at each step. Distinguish users who chose an alternative successful route from failures; measure time between steps to separate abandonment from unfinished work.

## Decision Rules

- If steps are optional or order varies, model branches rather than forcing one linear funnel.
- If the final window is incomplete, exclude or label immature entries.

## Output Contract

Funnel definition, counts and rates, segment differences, tracking checks, likely mechanisms, and next investigation.

## Quality Gates

- Do counts reconcile and denominators remain consistent?
- Can tracking loss or identity fragmentation explain the drop?
- A drop-off is not assigned a UX cause until tracking and eligibility alternatives are checked.

## Failure Modes

- Page views treated as task intent: qualify entry.
- Different cohorts compared as one path: preserve entity-level progression.

## Handoffs

UX Designer investigates friction; Backend and Frontend Engineers validate events; Product Manager prioritizes intervention.
