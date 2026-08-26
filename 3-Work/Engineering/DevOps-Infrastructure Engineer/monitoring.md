# Monitoring

Context: [DevOps-Infrastructure Engineer](README.md).

## Purpose

Create signals and alerts that detect user-impacting failure with actionable ownership.

## Activate When

A service lacks useful visibility or alerts are noisy.

## Do Not Use When

Logging records events; monitoring must support decisions rather than collect every metric.

## Required Context

**Needed:** Critical user outcomes, measurable signals, service expectations, and response capacity.

**Can be deferred or bounded:** Thresholds may begin provisional with review; alerts still need an actionable owner.

## Workflow

1. Map user outcomes to measurable success, latency, freshness, and correctness signals.
2. Define collection, denominator, sampling, and missing-data behavior.
3. Choose alert conditions that require action and distinguish symptoms from diagnostic context.
4. Test alert delivery, routing, suppression, and recovery with safe failure simulation.

## Signal Contract

Define numerator, denominator, time window, missing-data handling, and alert action. Use symptom signals for paging and diagnostics for investigation. Test a real delivery path to the operator and a telemetry outage; a dashboard existing does not prove anyone will notice failure.

## Decision Rules

- If no operator action follows an alert, use a dashboard or revise the alert.
- If telemetry can disappear during failure, monitor the monitoring path.

## Output Contract

SLIs or health signals, thresholds, dashboards, alerts, runbook links, and ownership.

## Quality Gates

- Can the team detect a meaningful failure before or promptly after user impact?
- Are false positives, alert volume, and response expectations sustainable?
- Each page can lead to a specific timely action and has a runbook or clear first diagnostic step.

## Failure Modes

- CPU threshold substitutes for user health: include outcome signals.
- Alert without owner or runbook: assign response.

## Handoffs

Product owner defines acceptable outcomes; engineers instrument; [reliability-review.md](reliability-review.md) evaluates service objectives.
