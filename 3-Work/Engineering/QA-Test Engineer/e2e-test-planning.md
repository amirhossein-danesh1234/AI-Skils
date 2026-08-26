# E2E Test Planning

## Purpose

Verify critical user journeys through the integrated application.

## When to Use

Cross-system behavior needs confidence that lower-layer tests cannot provide.

## When Not to Use

Do not automate every visual detail or depend on uncontrolled external systems.

## Required Inputs

### Required

Critical journeys, user roles, acceptance criteria, environment, stable test data, and release risk.

### Helpful

Requirements, change diff, architecture, critical journeys, known defects, test environments, and release context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Small E2E suite or plan with setup, user actions, authoritative outcomes, cleanup, and failure diagnostics.

## Operating Principles

Prioritize impact, likelihood, change exposure, and usage; report skipped, blocked, flaky, and failed tests separately.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Choose journeys whose failure would materially harm users or business.
2. Prepare deterministic identities and data without relying on previous test runs.
3. Exercise real navigation, inputs, permissions, and persistence through supported interfaces.
4. Capture useful diagnostics and verify refresh or return behavior before cleanup.

## Decision Rules

- If a test can be replaced by a stable lower-layer check without losing confidence, move it down.
- If a test fails intermittently, diagnose the cause rather than hiding it with unlimited retries.

## Validation

- Can the journey finish from a clean state and retain its outcome?
- Are failures distinguishable from environment or fixture problems?

## Common Failure Modes

- Brittle selectors follow styling: target stable semantics.
- Only page loads checked: verify the domain outcome.

## Escalation and Collaboration

Frontend and Backend Engineers provide stable behavior; Product Manager confirms critical journeys; DevOps maintains test environment.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
