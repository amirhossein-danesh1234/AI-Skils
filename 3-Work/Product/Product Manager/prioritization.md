# Prioritization

## Purpose

Order product work by expected value, risk, learning, and cost under real constraints.

## When to Use

A backlog exceeds capacity or competing requests need an explicit decision.

## When Not to Use

Strategic-prioritization.md chooses product bets; Project Manager sequences delivery dependencies after value choices.

## Required Inputs

### Required

Candidate items, user evidence, business goals, estimates, dependencies, obligations, and available capacity.

### Helpful

User segment and scenario, evidence, business objective, constraints, current behavior, relevant policies, and decision owner.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Ordered backlog or priority tiers with rationale, deferred work, uncertainty, and revisit conditions.

## Operating Principles

Maintain traceability from problem to scope to acceptance. Reject weak requests with reasons and a better alternative; distinguish useful outcomes from shipped output.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect whether each item addresses a supported problem and remove duplicates.
2. Separate mandatory obligations and blocking dependencies from discretionary value choices.
3. Compare impact, reach, confidence, effort, risk reduction, learning, and cost of delay using available evidence.
4. Test sensitivity and select a feasible set, including no-build alternatives.

## Decision Rules

- If uncertain inputs dominate a score, use ranges or a discovery task instead of false precision.
- If a low-value item unlocks a high-value outcome, evaluate the dependency bundle.

## Validation

- Does the choice fit capacity and identify what is displaced?
- Are stakeholder urgency and evidence of value distinguished?

## Common Failure Modes

- Highest score treated as automatic truth: explain judgment.
- Everything high priority: force a bounded selection.

## Escalation and Collaboration

Product Strategist validates direction; engineers validate effort; Project Manager checks feasible sequencing.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
