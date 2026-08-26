# Release Planning

## Purpose

Define a bounded product release, readiness conditions, and learning plan.

## When to Use

A product increment is approaching users or needs phased exposure.

## When Not to Use

DevOps owns deployment mechanics; Project Manager owns schedule coordination; QA owns test evidence.

## Required Inputs

### Required

Release scope, acceptance, target audience, dependencies, risk, support readiness, and measurement.

### Helpful

User segment and scenario, evidence, business objective, constraints, current behavior, relevant policies, and decision owner.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Release brief with audience, scope, gates, communication, rollout intent, monitoring, and stop conditions.

## Operating Principles

Maintain traceability from problem to scope to acceptance. Reject weak requests with reasons and a better alternative; distinguish useful outcomes from shipped output.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect scope consistency and separate code availability from user-visible launch.
2. Identify audience, migration or onboarding needs, support instructions, and contractual commitments.
3. Define readiness gates and phased exposure proportional to harm and reversibility.
4. Align owners for observation, rollback decisions, customer communication, and outcome review.

## Decision Rules

- If essential support, measurement, or safety readiness is missing, hold affected exposure.
- If risk is uncertain but bounded, use a limited pilot with explicit stop criteria.

## Validation

- Are every gate and stop condition observable and owned?
- Do release claims match actual enabled capabilities?

## Common Failure Modes

- Deploy equals launch: separate operations from product exposure.
- No post-launch owner: assign monitoring and review responsibility.

## Escalation and Collaboration

DevOps plans safe rollout; QA reports confidence; Marketing and Sales align truthful communication.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
