# User Flow

## Purpose

Specify paths through a user task, including decisions and recovery.

## When to Use

A task needs clear navigation and state transitions before implementation.

## When Not to Use

Journey mapping covers the wider experience; UI layout is a separate decision.

## Required Inputs

### Required

Task goal, actors, entry points, rules, current flow, and constraints.

### Helpful

User tasks, research evidence, current screens and flows, constraints, accessibility needs, and business rules.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Flow with entry and exit conditions, decisions, states, errors, permissions, and recovery paths.

## Operating Principles

Separate observed behavior from interpretation. Optimize comprehension and task completion, not screen count or visual novelty.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect existing behavior and identify the authoritative state for each step.
2. Trace the shortest valid path to the user outcome.
3. Add branches for missing data, cancellation, denial, timeout, repeated actions, and return visits.
4. Review navigation, back behavior, saved progress, and consistency across entry points.

## Decision Rules

- If two states look identical but allow different actions, expose the difference to the user.
- If a step does not change information, consent, or control, consider removing it.

## Validation

- Can every path terminate, recover, or clearly explain a block?
- Do frontend and backend state assumptions agree?

## Common Failure Modes

- Screen sequence without decision logic: annotate conditions.
- Dead ends after errors: define recovery or support.

## Escalation and Collaboration

Product Manager resolves business rules; Backend Engineer checks state transitions; Frontend Engineer implements navigation.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
