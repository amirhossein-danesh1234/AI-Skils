# Feature Definition

## Purpose

Define a bounded product capability justified by an accepted problem.

## When to Use

A solution path is selected and the team needs to agree what capability is intended.

## When Not to Use

Use problem-definition.md for unclear needs and prd-writing.md for a detailed delivery specification.

## Required Inputs

### Required

Accepted problem, target users, desired outcome, alternatives considered, constraints, and business rules.

### Helpful

User segment and scenario, evidence, business objective, constraints, current behavior, relevant policies, and decision owner.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Feature brief with scenarios, scope, exclusions, states, dependencies, success signals, and open decisions.

## Operating Principles

Maintain traceability from problem to scope to acceptance. Reject weak requests with reasons and a better alternative; distinguish useful outcomes from shipped output.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect current behavior and existing capabilities that might satisfy the need.
2. Define the smallest coherent user outcome, including who can initiate and complete it.
3. Map normal, empty, error, permission, and recovery states at capability level.
4. Identify integrations and policy decisions; compare the benefit with maintenance and operational burden.

## Decision Rules

- If the capability requires unresolved policy, mark the decision owner and block only the affected scope.
- If an existing capability can be adjusted, prefer reuse unless it creates greater complexity.

## Validation

- Can the feature be explained without prescribing implementation?
- Are exclusions and failure behavior sufficient to prevent scope ambiguity?

## Common Failure Modes

- Feature list without outcome: anchor to a scenario.
- Happy path only: include recovery and permission states.

## Escalation and Collaboration

UX Designer owns interaction detail; Architect checks structural impact; Product Analyst defines measurement.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
