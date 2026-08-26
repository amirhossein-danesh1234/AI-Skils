# Design System

## Purpose

Create a maintainable contract connecting visual rules, components, and usage.

## When to Use

Multiple screens or teams need consistent design decisions.

## When Not to Use

Do not build a large component catalog without demonstrated reuse or replace product discovery.

## Required Inputs

### Required

Existing UI inventory, code components, tokens, brand rules, team ownership, and recurring inconsistencies.

### Helpful

Approved flow, content, reference designs or brand constraints, existing tokens, components, and target devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

System scope, tokens, component inventory, usage rules, ownership, versioning, and adoption plan.

## Operating Principles

Use consistent visual rules, measurable contrast and sizing checks, and realistic content; justify exceptions instead of adding arbitrary tokens.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Audit repeated patterns and identify the inconsistencies with real maintenance or usability cost.
2. Define a minimal token and component foundation with clear semantic roles.
3. Specify states, accessibility expectations, composition, and exceptions for adopted components.
4. Assign ownership, contribution rules, compatibility expectations, and incremental migration.

## Decision Rules

- If a pattern has no repeated need, leave it local until evidence justifies standardization.
- If adoption cost exceeds current benefit, deliver a smaller foundation first.

## Validation

- Do design and code names and states map clearly?
- Can a contributor decide reuse versus extension and understand migration impact?

## Common Failure Modes

- Catalog without governance: assign maintenance responsibility.
- Abstract completeness over adoption: prioritize used patterns.

## Escalation and Collaboration

Frontend Engineer owns implementation contracts; UX Designer validates interaction consistency; Product Manager negotiates migration scope.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
