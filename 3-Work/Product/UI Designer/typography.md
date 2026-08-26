# Typography

## Purpose

Define readable text roles and behavior across real content.

## When to Use

A product needs type roles or text is inconsistent or difficult to read.

## When Not to Use

Do not invent brand identity or substitute typography for content clarity.

## Required Inputs

### Required

Fonts or brand constraints, languages, text roles, device contexts, and existing styles.

### Helpful

Approved flow, content, reference designs or brand constraints, existing tokens, components, and target devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Type scale and role mapping with weight, line height, wrapping, fallback, and language checks.

## Operating Principles

Use consistent visual rules, measurable contrast and sizing checks, and realistic content; justify exceptions instead of adding arbitrary tokens.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect available fonts, licensing constraints, glyph coverage, and actual content lengths.
2. Assign roles for headings, body, labels, controls, and data rather than styling each screen independently.
3. Set readable size, line height, measure, and contrast in the intended context.
4. Test zoom, long labels, numbers, mixed scripts, and fallback fonts.

## Decision Rules

- If a font lacks required glyphs or a usable license, choose an approved fallback.
- If text must be shrunk to fit, revisit layout or wording first.

## Validation

- Are hierarchy and legibility preserved at supported sizes and zoom?
- Do mixed-language and numeric strings align and wrap sensibly?

## Common Failure Modes

- Mockup-only font fails in production: verify availability.
- Truncation hides essential meaning: define expansion or wrapping.

## Escalation and Collaboration

Frontend Engineer validates font loading and rendering; Product Manager approves material copy changes.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
