# Responsive Implementation

## Purpose

Implement adaptive layouts that preserve functionality across supported conditions.

## When to Use

Approved responsive rules need code or a layout breaks at particular sizes.

## When Not to Use

Do not invent missing mobile behavior or remove functionality to fit a screenshot.

## Required Inputs

### Required

Design rules, supported viewports, content variants, existing CSS conventions, and input methods.

### Helpful

Repository instructions, approved UI and behavior, runtime versions, API contracts, existing tests, and supported devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Responsive implementation with documented adaptations and verified viewport/content states.

## Operating Principles

Follow existing conventions, keep state minimal, test realistic interactions, and distinguish compilation from verified user behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect current layout primitives and identify content-driven breakpoints.
2. Implement flexible sizing, reflow, overflow, and navigation using existing conventions.
3. Test narrow, wide, intermediate, zoomed, and long-content states with real interaction.
4. Check reading order, focus visibility, touch controls, and orientation before finalizing.

## Decision Rules

- If a required action is hidden at a breakpoint, provide an equivalent accessible route.
- If fixed dimensions cause clipping, fix layout constraints rather than shrinking content arbitrarily.

## Validation

- Can the primary task finish at every supported size?
- Are horizontal overflow, overlays, keyboard access, and text zoom checked?

## Common Failure Modes

- Only two screenshots tested: inspect intermediate widths.
- CSS visual order differs from focus order: align the structure.

## Escalation and Collaboration

UI Designer resolves visual adaptation; UX Designer approves interaction changes; QA validates device coverage.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
