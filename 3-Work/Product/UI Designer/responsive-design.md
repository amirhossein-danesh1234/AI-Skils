# Responsive Design

## Purpose

Specify how visual composition adapts to content and available space.

## When to Use

A design must work across viewport sizes and input contexts.

## When Not to Use

Frontend responsive-implementation.md handles code; do not merely shrink a desktop mockup.

## Required Inputs

### Required

Approved content and flow, priority hierarchy, component constraints, and target devices.

### Helpful

Approved flow, content, reference designs or brand constraints, existing tokens, components, and target devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Responsive rules for reflow, navigation, density, sizing, overflow, and state variants.

## Operating Principles

Use consistent visual rules, measurable contrast and sizing checks, and realistic content; justify exceptions instead of adding arbitrary tokens.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect minimum usable widths and content-driven breakpoints.
2. Decide what reflows, stacks, scrolls, or changes navigation while preserving task access.
3. Specify behavior between reference widths, not only at two screenshots.
4. Stress-test long text, zoom, keyboard focus, orientation, and touch interaction.

## Decision Rules

- If hiding content removes required information or action, provide an equivalent accessible path.
- If a table cannot reflow without losing comparison, specify deliberate accessible horizontal navigation.

## Validation

- Can the same primary task finish on each supported layout?
- Are intermediate widths and content extremes covered?

## Common Failure Modes

- Device labels replace rules: define content constraints.
- Desktop order copied blindly: preserve logical reading and focus order.

## Escalation and Collaboration

UX Designer approves interaction changes; Frontend Engineer verifies actual breakpoints and overflow.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
