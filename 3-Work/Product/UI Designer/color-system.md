# Color System

## Purpose

Define semantic color roles with accessible and consistent state communication.

## When to Use

Colors are inconsistent or state meaning relies on arbitrary hues.

## When Not to Use

Do not claim accessibility from palette selection alone or change brand without approval.

## Required Inputs

### Required

Brand palette, backgrounds, text roles, states, themes, and accessibility target.

### Helpful

Approved flow, content, reference designs or brand constraints, existing tokens, components, and target devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Semantic tokens, contrast evidence, state mappings, theme behavior, and non-color cues.

## Operating Principles

Use consistent visual rules, measurable contrast and sizing checks, and realistic content; justify exceptions instead of adding arbitrary tokens.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect actual foreground/background pairs and existing status meanings.
2. Assign colors by semantic role, separating brand, action, feedback, and surfaces.
3. Check relevant contrast requirements in real states including disabled, focus, and selected variants.
4. Pair status color with text, icon, or structure and test theme and image-background cases.

## Decision Rules

- If a brand color fails a required contrast use, adjust its role or use an approved variant.
- If color is the only signal, add a second cue.

## Validation

- Are critical text and control pairs checked against the chosen accessibility target?
- Do themes preserve meaning and contrast?

## Common Failure Modes

- Palette swatches mistaken for UI contrast: test actual pairs.
- Red/green alone communicates status: add labels or symbols.

## Escalation and Collaboration

Frontend Engineer verifies rendered contrast; UX Designer confirms status meaning; use current W3C guidance for specific criteria.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
