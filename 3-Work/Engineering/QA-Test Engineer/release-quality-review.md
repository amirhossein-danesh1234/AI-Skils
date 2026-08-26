# Release Quality Review

## Purpose

Translate actual test evidence into a transparent release-risk recommendation.

## When to Use

A release owner needs a go, hold, or conditional recommendation.

## When Not to Use

QA does not accept business risk on behalf of the release owner or infer success from build completion.

## Required Inputs

### Required

Release scope/version, acceptance, executed tests, known defects, deployment readiness, and risk tolerance.

### Helpful

Requirements, change diff, architecture, critical journeys, known defects, test environments, and release context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Quality readout with coverage, pass/fail/skip/block counts, critical defects, residual risks, and recommendation.

## Operating Principles

Prioritize impact, likelihood, change exposure, and usage; report skipped, blocked, flaky, and failed tests separately.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Confirm the tested artifact matches the release candidate and scope.
2. Review evidence for critical journeys, permissions, data integrity, recovery, and changed contracts.
3. Assess known defects by user impact, workaround, exposure, and detectability.
4. Recommend release, limited exposure, or hold with explicit conditions and owner acceptance.

## Decision Rules

- If a critical invariant or security boundary is unverified or failing, recommend hold or remove affected exposure.
- If remaining risk is bounded and reversible, propose conditional rollout with monitoring and stop rules.

## Validation

- Are all claims backed by executed evidence or clearly labeled assessment?
- Are release gates, residual-risk owners, and untested areas visible?

## Common Failure Modes

- No known bugs becomes proof of safety: report coverage limits.
- Skipped tests silently counted as pass: separate statuses.

## Escalation and Collaboration

DevOps verifies rollout and recovery; Product Manager owns product readiness; authorized release owner decides.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
