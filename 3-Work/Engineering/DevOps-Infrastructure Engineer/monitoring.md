# Monitoring

## Purpose

Create signals and alerts that detect user-impacting failure with actionable ownership.

## When to Use

A service lacks useful visibility or alerts are noisy.

## When Not to Use

Logging records events; monitoring must support decisions rather than collect every metric.

## Required Inputs

### Required

Critical journeys, service objectives, dependencies, incident history, and on-call capacity.

### Helpful

Actual infrastructure and listeners, release process, identities, dependencies, service objectives, secrets handling, and current incident state.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

SLIs or health signals, thresholds, dashboards, alerts, runbook links, and ownership.

## Operating Principles

Inspect before mutation; use immutable or traceable releases, least privilege, explicit stop conditions, and real service checks.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Map user outcomes to measurable success, latency, freshness, and correctness signals.
2. Define collection, denominator, sampling, and missing-data behavior.
3. Choose alert conditions that require action and distinguish symptoms from diagnostic context.
4. Test alert delivery, routing, suppression, and recovery with safe failure simulation.

## Decision Rules

- If no operator action follows an alert, use a dashboard or revise the alert.
- If telemetry can disappear during failure, monitor the monitoring path.

## Validation

- Can the team detect a meaningful failure before or promptly after user impact?
- Are false positives, alert volume, and response expectations sustainable?

## Common Failure Modes

- CPU threshold substitutes for user health: include outcome signals.
- Alert without owner or runbook: assign response.

## Escalation and Collaboration

Product owner defines acceptable outcomes; engineers instrument; reliability-review.md evaluates service objectives.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
