# Information Architecture

## Purpose

Organize content and actions so users can find and understand them.

## When to Use

Navigation, categories, or labels obscure tasks and content relationships.

## When Not to Use

Do not use taxonomy work to redesign product strategy or visual styling.

## Required Inputs

### Required

Content inventory, user tasks, terminology, permissions, and current navigation.

### Helpful

User tasks, research evidence, current screens and flows, constraints, accessibility needs, and business rules.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Proposed hierarchy, labels, navigation rules, content ownership, and findability checks.

## Operating Principles

Separate observed behavior from interpretation. Optimize comprehension and task completion, not screen count or visual novelty.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inventory actual content and identify duplicate or missing destinations.
2. Group by user intent and mental model, not internal departments by default.
3. Define labels and hierarchy with shallow paths to frequent tasks.
4. Test representative find tasks and permission-dependent visibility; record ambiguous labels.

## Decision Rules

- If a category mixes incompatible user meanings, split or relabel it.
- If the same content appears in several paths, define one source and multiple entry links.

## Validation

- Can representative users predict where a task belongs?
- Are labels consistent and inaccessible destinations handled clearly?

## Common Failure Modes

- Org chart copied into navigation: use task evidence.
- Deep hierarchy hides important content: test path cost.

## Escalation and Collaboration

Product Manager owns content scope; UI Designer expresses hierarchy; Frontend Engineer checks routing and access states.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
