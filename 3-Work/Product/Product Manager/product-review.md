# Product Review

## Purpose

Evaluate whether a product increment achieved its intended user and business outcome.

## When to Use

A prototype, release, or live feature needs a continue, revise, expand, or stop decision.

## When Not to Use

QA release-quality-review.md assesses test confidence; this skill evaluates product value and learning.

## Required Inputs

### Required

Original objective, acceptance scope, observed behavior, outcome data, feedback, and operational costs.

### Helpful

User segment and scenario, evidence, business objective, constraints, current behavior, relevant policies, and decision owner.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Outcome review with evidence, deviations, unintended effects, decision, and next learning or correction.

## Operating Principles

Maintain traceability from problem to scope to acceptance. Reject weak requests with reasons and a better alternative; distinguish useful outcomes from shipped output.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect the original decision and expected outcomes before looking at presentation polish.
2. Compare actual adoption and task success with the relevant baseline and segment.
3. Reconcile qualitative feedback, quantitative signals, defects, and support burden.
4. Decide whether to continue, revise, narrow, or stop and update assumptions.

## Decision Rules

- If acceptance passes but user value is absent, do not call the product successful.
- If measurement is invalid or immature, recommend an evidence repair or later review.

## Validation

- Are outcomes distinguished from output and attribution limits stated?
- Does the next action address the largest remaining uncertainty or failure?

## Common Failure Modes

- Demo enthusiasm substituted for results: inspect real use.
- Confirmation bias: include disconfirming feedback and costs.

## Escalation and Collaboration

Product Analyst validates evidence; UX investigates friction; engineering explains reliability; Product Strategist assesses direction.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
