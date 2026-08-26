# Spacing System

## Purpose

Define consistent spacing relationships for a coherent interface.

## When to Use

Spacing feels arbitrary or components need shared rhythm.

## When Not to Use

Do not use spacing tokens to compensate for a broken layout or unclear hierarchy.

## Required Inputs

### Required

Existing tokens, component inventory, density needs, and reference screens.

### Helpful

Approved flow, content, reference designs or brand constraints, existing tokens, components, and target devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Spacing scale, semantic usage rules, component mappings, and justified exceptions.

## Operating Principles

Use consistent visual rules, measurable contrast and sizing checks, and realistic content; justify exceptions instead of adding arbitrary tokens.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Measure existing repeated gaps and identify intentional versus accidental variation.
2. Choose a small scale appropriate to density and touch contexts.
3. Assign spacing by relationship: within controls, between related fields, and between sections.
4. Apply the rules to dense and sparse screens and record exceptions with reasons.

## Decision Rules

- If two gaps express the same relationship, prefer one token.
- If density impairs readability or target separation, increase space or change layout.

## Validation

- Are tokens used consistently across comparable components?
- Do changes preserve hierarchy and usable target spacing?

## Common Failure Modes

- Many near-identical tokens: consolidate meaningful roles.
- Rigid scale harms content: allow documented exceptions.

## Escalation and Collaboration

UI component-design.md and layout-design.md consume the spacing rules; Frontend Engineer maps tokens to code.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
