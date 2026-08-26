# Component Design

## Purpose

Specify reusable visual components with complete states and usage boundaries.

## When to Use

Repeated interface patterns need a consistent visual contract.

## When Not to Use

Frontend Engineer owns component code architecture; UX Designer owns interaction policy.

## Required Inputs

### Required

Approved behavior, existing components and tokens, content variants, and accessibility requirements.

### Helpful

Approved flow, content, reference designs or brand constraints, existing tokens, components, and target devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Component anatomy, variants, states, sizing, content rules, and appropriate-use guidance.

## Operating Principles

Use consistent visual rules, measurable contrast and sizing checks, and realistic content; justify exceptions instead of adding arbitrary tokens.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect existing patterns and decide whether a component already satisfies the need.
2. Define anatomy and semantic variants before cosmetic options.
3. Specify default, hover, focus, active, disabled, loading, error, empty, and selected states as applicable.
4. Test composition, long content, small viewports, and keyboard-visible state.

## Decision Rules

- If variants express unrelated tasks, use separate components rather than one configuration-heavy control.
- If a new variant duplicates an existing semantic role, reuse it.

## Validation

- Can implementation distinguish every meaningful state without guessing?
- Are tokens and behavior consistent with the design system?

## Common Failure Modes

- Only default state designed: enumerate applicable states.
- Variant explosion: require a real use case for each variant.

## Escalation and Collaboration

UX Designer approves behavior; Frontend Engineer maps the specification to accessible APIs.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
