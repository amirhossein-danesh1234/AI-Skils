# User Story Design

## Purpose

Express a useful slice of user value with enough context for refinement.

## When to Use

A capability needs user-centered slices for discussion and delivery.

## When Not to Use

Stories are not a substitute for complex business rules, contracts, or a complete PRD.

## Required Inputs

### Required

User role, scenario, outcome, current capability, constraints, and dependencies.

### Helpful

User segment and scenario, evidence, business objective, constraints, current behavior, relevant policies, and decision owner.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Stories with value, context, acceptance, exclusions, and slicing rationale.

## Operating Principles

Maintain traceability from problem to scope to acceptance. Reject weak requests with reasons and a better alternative; distinguish useful outcomes from shipped output.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect the end-to-end scenario and identify independently useful outcomes.
2. Write the actor’s need and reason using the user’s language rather than technical layers.
3. Attach concrete examples and essential rule references without hiding complexity in a sentence.
4. Split by coherent behavior or risk, preserving a usable vertical outcome.

## Decision Rules

- If a slice produces no observable user or operational value, reconsider a technical-layer split.
- If several actors have conflicting needs, create distinct scenarios rather than a universal user.

## Validation

- Can each story be demonstrated and accepted?
- Do stories together cover the intended scenario without duplicated scope?

## Common Failure Modes

- Formulaic sentence with no context: add real examples.
- Tiny fragments inflate backlog: preserve a meaningful outcome.

## Escalation and Collaboration

UX Designer confirms task coherence; engineers assess slicing; QA checks acceptance.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
