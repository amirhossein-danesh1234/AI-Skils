# Dependency Analysis

## Purpose

Identify product-level prerequisites and consequences before scope is committed.

## When to Use

A feature crosses teams, policies, data, vendors, or customer workflows.

## When Not to Use

Project Manager manages delivery dependency dates; Architect owns technical coupling design.

## Required Inputs

### Required

Proposed scope, actors, systems, policies, data flows, and known external parties.

### Helpful

User segment and scenario, evidence, business objective, constraints, current behavior, relevant policies, and decision owner.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Dependency map with type, owner, required condition, evidence, criticality, and fallback.

## Operating Principles

Maintain traceability from problem to scope to acceptance. Reject weak requests with reasons and a better alternative; distinguish useful outcomes from shipped output.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Walk each user scenario and list inputs, approvals, capabilities, and downstream consumers.
2. Separate hard prerequisites from preferred sequence or assumed convenience.
3. Check circular dependencies and failure propagation into user outcomes.
4. Seek owner confirmation and compare decoupling, reduced scope, manual fallback, or delay.

## Decision Rules

- If a prerequisite has no owner or feasible delivery path, mark affected scope unready.
- If a dependency can be removed without losing the outcome, prefer the simpler scope.

## Validation

- Does every hard dependency have a verifiable completion condition?
- Are external lead times and policy approvals included?

## Common Failure Modes

- Only technical dependencies counted: include legal and operational prerequisites.
- Unconfirmed promise treated as available: label confidence.

## Escalation and Collaboration

Architect evaluates coupling; Project Manager coordinates dates; relevant policy owner resolves approvals.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
