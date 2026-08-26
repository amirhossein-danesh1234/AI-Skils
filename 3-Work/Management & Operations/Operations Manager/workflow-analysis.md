# Workflow Analysis

## Purpose

Describe how recurring work actually moves and where it loses time or quality.

## When to Use

A process is poorly understood or improvement proposals lack evidence.

## When Not to Use

Process-design.md proposes the future state; analysis must first preserve actual behavior.

## Required Inputs

### Required

Work samples, timestamps, roles, handoffs, tools, and observed outcomes.

### Helpful

Actual work samples, process boundaries, volumes, timing, defects, roles, tools, and service expectations.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Current-state map with cycle/wait time, rework, variation, bottleneck hypotheses, and evidence gaps.

## Operating Principles

Improve end-to-end flow and quality, not one team’s utilization at the expense of downstream queues.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Trace representative completed and failed cases from entry to exit.
2. Separate active work, waiting, approval, transfer, and rework time.
3. Compare documented procedure with actual workarounds and exceptions.
4. Identify patterns that explain delay or defects without prescribing a solution prematurely.

## Decision Rules

- If timestamps reflect system entry rather than real work, state the measurement limitation.
- If one case is atypical, collect additional evidence before generalizing.

## Validation

- Does the map account for the whole elapsed time?
- Are observed facts separated from inferred causes?

## Common Failure Modes

- Official process mistaken for reality: inspect cases.
- Average hides tail delays: examine variation.

## Escalation and Collaboration

Bottleneck-analysis.md tests constraints; Team Manager clarifies roles; operators validate the map.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
