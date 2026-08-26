# Requirement Analysis

## Purpose

Resolve ambiguity, conflict, and incompleteness in proposed requirements.

## When to Use

Requirements arrive from multiple sources or contain unclear rules and dependencies.

## When Not to Use

This is not backlog ordering or permission to change stakeholder intent silently.

## Required Inputs

### Required

Source requirements, business rules, current behavior, constraints, and requirement owners.

### Helpful

User segment and scenario, evidence, business objective, constraints, current behavior, relevant policies, and decision owner.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Normalized requirement set with conflicts, assumptions, traceability, gaps, and resolution decisions.

## Operating Principles

Maintain traceability from problem to scope to acceptance. Reject weak requests with reasons and a better alternative; distinguish useful outcomes from shipped output.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect source wording and distinguish needs, constraints, solutions, and preferences.
2. Rewrite ambiguous statements into observable behavior without inventing policy.
3. Check actor, preconditions, data, state transitions, exceptions, and nonfunctional constraints.
4. Resolve contradictions with the responsible owner and document the effect on scope and acceptance.

## Decision Rules

- If two requirements cannot both hold, expose the conflict rather than choosing the easier one.
- If wording is merely a preference, label it and assess alternatives.

## Validation

- Are requirements individually testable and collectively consistent?
- Are source intent and unresolved decisions traceable?

## Common Failure Modes

- Silent assumption becomes requirement: label provenance.
- Unbounded adjectives such as fast: request a contextual measurable target.

## Escalation and Collaboration

Product owner resolves policy; Architect evaluates quality constraints; QA challenges testability.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
