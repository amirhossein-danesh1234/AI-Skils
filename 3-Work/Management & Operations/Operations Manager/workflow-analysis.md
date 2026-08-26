# Workflow Analysis

Context: [Operations Manager](README.md).

## Purpose

Describe how recurring work actually moves and where it loses time or quality.

## Activate When

A process is poorly understood or improvement proposals lack evidence.

## Do Not Use When

[Process-design.md](process-design.md) proposes the future state; analysis must first preserve actual behavior.

## Required Context

**Needed:** Representative completed/failed work, timestamps, roles, and actual handoffs.

**Can be deferred or bounded:** Official documentation is context, not proof of practice; missing timestamps limit time estimates.

## Workflow

1. Trace representative completed and failed cases from entry to exit.
2. Separate active work, waiting, approval, transfer, and rework time.
3. Compare documented procedure with actual workarounds and exceptions.
4. Identify patterns that explain delay or defects without prescribing a solution prematurely.

## Elapsed-Time Reconciliation

Trace cases from arrival to accepted completion and account for active work, queues, transfer, approval, and rework. Check whether system timestamps represent real work or delayed data entry. Preserve different case types and tail delays instead of forcing one average idealized flow.

## Decision Rules

- If timestamps reflect system entry rather than real work, state the measurement limitation.
- If one case is atypical, collect additional evidence before generalizing.

## Output Contract

Current-state map with cycle/wait time, rework, variation, bottleneck hypotheses, and evidence gaps.

## Quality Gates

- Does the map account for the whole elapsed time?
- Are observed facts separated from inferred causes?
- The map explains the whole observed elapsed time or labels the unobserved remainder.

## Failure Modes

- Official process mistaken for reality: inspect cases.
- Average hides tail delays: examine variation.

## Handoffs

[Bottleneck-analysis.md](bottleneck-analysis.md) tests constraints; Team Manager clarifies roles; operators validate the map.
