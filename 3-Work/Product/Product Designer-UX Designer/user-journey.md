# User Journey

## Purpose

Map the user’s experience across stages, channels, and handoffs.

## When to Use

A problem spans more than one screen or interaction session.

## When Not to Use

Use user-flow.md for detailed in-product paths; do not invent emotions without evidence.

## Required Inputs

### Required

User goal, segment, triggers, channels, observed steps, and service boundaries.

### Helpful

User tasks, research evidence, current screens and flows, constraints, accessibility needs, and business rules.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Journey map with stages, user actions, touchpoints, friction, evidence, and improvement opportunities.

## Operating Principles

Separate observed behavior from interpretation. Optimize comprehension and task completion, not screen count or visual novelty.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect what happens before and after the product interaction.
2. Identify each stage’s user objective, action, expectation, and observed outcome.
3. Map handoffs, waiting, repeated effort, and offline workarounds.
4. Prioritize friction by task impact and evidence, then route local flow design separately.

## Decision Rules

- If the journey differs materially by segment, map separate variants.
- If a touchpoint lies outside product control, identify a partner or operational dependency.

## Validation

- Does the map cover the real end-to-end outcome rather than only owned screens?
- Are observed emotions distinguished from inferred ones?

## Common Failure Modes

- Decorative journey with no decisions: name improvement opportunities.
- Happy path excludes service failures: add recovery stages.

## Escalation and Collaboration

Operations Manager owns service handoffs; Product Manager prioritizes opportunities; UI Designer is consulted only after behavior is clear.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
