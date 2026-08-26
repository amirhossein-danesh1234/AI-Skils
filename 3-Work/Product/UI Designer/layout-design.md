# Layout Design

## Purpose

Arrange approved content into stable, readable screen structures.

## When to Use

A page needs a layout or a layout fails under realistic content.

## When Not to Use

Responsive behavior across widths belongs with responsive-design.md; do not redefine navigation strategy.

## Required Inputs

### Required

Content inventory, flow, target viewports, existing grid, and component constraints.

### Helpful

Approved flow, content, reference designs or brand constraints, existing tokens, components, and target devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Layout specification with grid, regions, alignment, sizing, overflow, and content stress cases.

## Operating Principles

Use consistent visual rules, measurable contrast and sizing checks, and realistic content; justify exceptions instead of adding arbitrary tokens.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect reading order, task sequence, and existing layout conventions.
2. Group related content and select a grid that supports primary and secondary regions.
3. Define width constraints, alignment, wrapping, and overflow instead of relying on fixed mockup dimensions.
4. Test dense, empty, long-text, translated, and permission-reduced content.

## Decision Rules

- If a layout needs arbitrary offsets for ordinary content, revise the structure.
- If columns make reading or input cramped, change composition rather than shrinking text.

## Validation

- Does reading and focus order match visual order?
- Can realistic content fit without overlap or hidden actions?

## Common Failure Modes

- Perfect sample content hides overflow: stress-test real extremes.
- Fixed heights clip text: define flexible sizing.

## Escalation and Collaboration

UX Designer approves grouping and task sequence; Frontend Engineer checks feasible layout rules.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
