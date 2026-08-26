# PRD Writing

## Purpose

Produce an implementation-ready product requirements document with traceable decisions.

## When to Use

An accepted feature or product increment needs a shared specification for design, engineering, and QA.

## When Not to Use

Do not use a PRD to manufacture evidence, approve unresolved policies, or replace technical design.

## Required Inputs

### Required

Accepted problem and feature brief, users, rules, constraints, stakeholders, and known dependencies.

### Helpful

User segment and scenario, evidence, business objective, constraints, current behavior, relevant policies, and decision owner.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

PRD covering goal, evidence, users, scenarios, scope, rules, states, errors, requirements, acceptance, measurement, risks, and open decisions.

## Operating Principles

Maintain traceability from problem to scope to acceptance. Reject weak requests with reasons and a better alternative; distinguish useful outcomes from shipped output.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect existing specifications, current behavior, approved rules, and stakeholder decisions; record contradictions.
2. Define goal, primary scenarios, scope, exclusions, and measurable outcomes before requirements.
3. Write uniquely identifiable requirements with actor, precondition, action, result, and relevant state or permission rules.
4. Trace requirements to acceptance criteria and design or engineering questions; separate decisions from assumptions.
5. Review edge behavior, rollout, support, data handling, dependencies, and unresolved owners before declaring readiness.

## PRD Contract and Readiness Gate

Use the following content contract; combine sections only when their meaning remains explicit.

- **Goal and problem:** primary user, triggering situation, current workaround, observed cost, evidence source, and desired change. Separate the business objective from the proposed feature.
- **Scenarios and scope:** entry conditions, actors, successful exit, supported variations, and explicit exclusions. Record why a smaller or non-software alternative is insufficient.
- **Requirements and rules:** stable identifiers; inputs and outputs; permissions; state transitions; limits; money, rounding, time, and retention rules where applicable. Link each rule to an approved source or an unresolved decision owner.
- **Failure and recovery:** empty and invalid data, duplicate submission, cancellation, timeout, partial completion, conflicting updates, unavailable dependencies, and return after interruption. Specify which effects persist and what users can safely retry.
- **Quality constraints:** measurable user-facing performance, accessibility, security, reliability, and compatibility expectations where relevant. Do not invent numeric targets; identify the owner who can set them.
- **Acceptance and measurement:** trace each requirement to observable acceptance and each desired outcome to a metric definition, baseline availability, observation window, and guardrails.
- **Delivery context:** dependencies, rollout assumptions, support needs, operational ownership, risks, open questions, and the decisions required before implementation or exposure.

Walk at least one normal scenario, one denied action, and one interrupted or repeated action from user intent through authoritative state and feedback. A polished document is not ready if implementation requires guessing policy. Mark independently ready slices separately from blocked slices; avoid blocking unrelated work for an optional detail.

## Decision Rules

- If a rule affects money, permissions, data retention, or legal obligations, require an explicit owner decision.
- If the team is small and scope narrow, use a compact PRD but retain states, acceptance, and open decisions.

## Validation

- Can QA derive tests and engineering identify contracts without guessing product behavior?
- Does each requirement support an in-scope scenario and each acceptance criterion trace to a requirement?

## Common Failure Modes

- Long prose hides ambiguity: use explicit rules and identifiers.
- PRD claims readiness with unowned blockers: separate ready scope from unresolved scope.

## Escalation and Collaboration

UX Designer validates flows; engineering checks feasibility; Security and Financial Analyst join only for material exposure; QA tests the specification.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
