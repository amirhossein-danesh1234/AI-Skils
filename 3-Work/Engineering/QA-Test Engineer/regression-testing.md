# Regression Testing

## Purpose

Check that a change preserves important existing behavior.

## When to Use

A fix, refactor, dependency update, or release could break prior capabilities.

## When Not to Use

Do not rerun unrelated expensive tests without considering change impact, or claim unrun suites passed.

## Required Inputs

### Required

Diff, dependency map, prior defects, existing suites, and release context.

### Helpful

Requirements, change diff, architecture, critical journeys, known defects, test environments, and release context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Regression selection, executed results, gaps, failures, and risk assessment.

## Operating Principles

Prioritize impact, likelihood, change exposure, and usage; report skipped, blocked, flaky, and failed tests separately.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Map changed code and contracts to affected consumers and historical failure patterns.
2. Select tests by impact and include an original defect reproduction when relevant.
3. Run in a controlled environment and separate failures, flakes, skips, and blocked checks.
4. Investigate regressions and rerun affected evidence after corrections.

## Decision Rules

- If a shared contract changes, include representative downstream consumers.
- If the full suite is impractical, disclose the selection and uncovered risk rather than claiming full validation.

## Validation

- Does evidence identify exact version, environment, and commands or cases?
- Are unresolved failures and skips explained?

## Common Failure Modes

- Green subset described as full suite: report scope precisely.
- Repeated retries hide flakes: investigate reliability.

## Escalation and Collaboration

Engineering owners fix regressions; release-quality-review.md interprets overall readiness.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
