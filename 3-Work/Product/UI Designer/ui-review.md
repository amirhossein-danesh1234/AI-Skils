# UI Review

## Purpose

Find visual implementation differences and consistency defects against an approved design.

## When to Use

A mockup or rendered interface needs visual quality review.

## When Not to Use

UX audit assesses task usability; code review assesses implementation correctness.

## Required Inputs

### Required

Approved reference, rendered screens, component rules, target sizes, and accepted deviations.

### Helpful

Approved flow, content, reference designs or brand constraints, existing tokens, components, and target devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Prioritized visual findings with location, expected/actual behavior, evidence, and correction scope.

## Operating Principles

Use consistent visual rules, measurable contrast and sizing checks, and realistic content; justify exceptions instead of adding arbitrary tokens.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect typography, spacing, alignment, hierarchy, color, and component states against the reference.
2. Compare multiple viewport and realistic content states, including loading and error.
3. Separate intentional adaptation from accidental mismatch.
4. Prioritize defects by readability, consistency, and task impact; retest corrected areas.

## Decision Rules

- If a difference improves constraints but changes behavior, request UX review before accepting it.
- If reference and design system conflict, resolve the source of truth rather than patching locally.

## Validation

- Are findings reproducible at specified viewport and state?
- Have corrected screens been visually reinspected rather than only rebuilt?

## Common Failure Modes

- Pixel perfection ignores usability: prioritize meaningful differences.
- Build passes treated as visual proof: inspect rendered output.

## Escalation and Collaboration

Frontend Engineer implements fixes; UX Designer resolves behavior changes; Product Manager approves scope changes.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
