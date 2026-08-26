# Component Design

## Purpose

Implement reusable frontend components with explicit behavior and accessible interfaces.

## When to Use

Repeated UI behavior needs a maintainable code component.

## When Not to Use

UI Designer defines visual variants; do not turn unrelated interactions into one configurable component.

## Required Inputs

### Required

Approved states, existing components, framework conventions, accessibility semantics, and consumers.

### Helpful

Repository instructions, approved UI and behavior, runtime versions, API contracts, existing tests, and supported devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Component API and implementation with state coverage, composition rules, tests, and usage examples appropriate to the codebase.

## Operating Principles

Follow existing conventions, keep state minimal, test realistic interactions, and distinguish compilation from verified user behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect existing components and identify the smallest shared behavior.
2. Define props, events, controlled versus internal state, and semantic HTML or platform roles.
3. Implement loading, disabled, error, focus, and content extremes without hidden side effects.
4. Test public behavior and representative composition rather than private implementation details.

## Decision Rules

- If two use cases share appearance but not behavior, compose primitives instead of adding many flags.
- If a component owns external effects, expose their contract and cancellation behavior.

## Validation

- Can keyboard and assistive-technology users operate it?
- Are invalid prop combinations prevented or handled clearly?

## Common Failure Modes

- Overgeneralized API: require real consumers for variants.
- Tests mirror implementation: assert observable behavior.

## Escalation and Collaboration

UI Designer confirms visual contract; UX Designer confirms interaction; QA validates critical compositions.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
