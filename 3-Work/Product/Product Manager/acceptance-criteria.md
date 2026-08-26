# Acceptance Criteria

## Purpose

Define observable conditions that prove an agreed requirement is satisfied.

## When to Use

A story or feature lacks a clear pass/fail oracle.

## When Not to Use

Do not invent requirements or prescribe tests that verify implementation details instead of behavior.

## Required Inputs

### Required

Approved requirement, actors, preconditions, rules, states, and supported environments.

### Helpful

User segment and scenario, evidence, business objective, constraints, current behavior, relevant policies, and decision owner.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Acceptance criteria with normal, boundary, error, permission, and recovery examples plus unresolved questions.

## Operating Principles

Maintain traceability from problem to scope to acceptance. Reject weak requests with reasons and a better alternative; distinguish useful outcomes from shipped output.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect the requirement and distinguish acceptance from optional quality improvements.
2. State initial conditions, action or event, and observable result for each material behavior.
3. Add boundary values, invalid inputs, repeated actions, and unauthorized actors where relevant.
4. Review each criterion for determinism and trace it to a requirement.

## Decision Rules

- If expected behavior is unknown, ask the policy owner; do not let a test encode an invented rule.
- If the result is subjective, define an agreed review method or measurable proxy.

## Validation

- Would independent reviewers reach the same pass/fail judgment?
- Are exceptions and negative permissions covered without expanding scope?

## Common Failure Modes

- Criteria repeat the feature title: define observable outcomes.
- UI-only checks miss persisted behavior: include authoritative effects.

## Escalation and Collaboration

QA converts criteria into tests; Backend and UX specialists resolve observable system and interaction behavior.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
