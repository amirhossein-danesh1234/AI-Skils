# Frontend Architecture

## Purpose

Structure client code around clear feature, state, and rendering boundaries.

## When to Use

A frontend needs organization or a cross-cutting change exceeds a local component.

## When Not to Use

Do not introduce a new framework or global store merely to standardize a small feature.

## Required Inputs

### Required

Repository instructions, framework/version, routes, data flows, state ownership, and performance constraints.

### Helpful

Repository instructions, approved UI and behavior, runtime versions, API contracts, existing tests, and supported devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Scoped architecture proposal or implementation with module boundaries, state ownership, dependencies, tests, and migration.

## Operating Principles

Follow existing conventions, keep state minimal, test realistic interactions, and distinguish compilation from verified user behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect existing feature organization, rendering modes, routing, and build constraints.
2. Map server state, local interaction state, URL state, and persistent preferences separately.
3. Choose boundaries that keep data access and side effects understandable without excessive abstraction.
4. Migrate incrementally and test navigation, hydration where relevant, and error recovery.

## Decision Rules

- If state is needed by one component subtree, keep it local unless another requirement justifies promotion.
- If a convention already works, extend it rather than creating a parallel architecture.

## Validation

- Are import dependencies and state ownership clear?
- Do route transitions, loading, and failure behavior remain correct?

## Common Failure Modes

- Folder taxonomy without runtime reasoning: trace a user interaction.
- Global state for convenience: minimize scope and synchronization.

## Escalation and Collaboration

Software Architect handles system boundaries; UX and UI define behavior and appearance; Backend Engineer owns server contracts.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
