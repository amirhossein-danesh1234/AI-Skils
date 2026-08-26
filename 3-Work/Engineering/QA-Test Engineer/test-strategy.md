# Test Strategy

## Purpose

Choose tests that provide useful confidence for the actual change and risk.

## When to Use

A feature, system, or release needs an evidence plan.

## When Not to Use

Do not maximize test count or mandate every test layer for every change.

## Required Inputs

### Required

Requirements, change scope, architecture, critical risks, environments, and release constraints.

### Helpful

Requirements, change diff, architecture, critical journeys, known defects, test environments, and release context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Risk-to-test strategy with layers, oracles, data, coverage, execution priorities, and exit criteria.

## Operating Principles

Prioritize impact, likelihood, change exposure, and usage; report skipped, blocked, flaky, and failed tests separately.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect critical user and business outcomes and the changed failure surface.
2. Rank failure scenarios by impact, likelihood, usage, security, and change exposure.
3. Choose the cheapest reliable test layer for each risk and reserve E2E for cross-system behavior.
4. Define fixtures, environments, ownership, execution order, and evidence required for release judgment.

## Risk-to-Evidence Matrix

For each material failure, identify the protected outcome, triggering condition, impact, test oracle, best test layer, environment fidelity, required data, owner, and execution priority. Mark coverage as planned, executed, passed, failed, blocked, skipped, or not applicable; do not collapse these states into a single completion percentage.

Use unit tests for isolated rules, integration tests for real boundary semantics, and E2E tests for critical journeys through the system. A mocked database cannot prove engine-specific isolation or constraint behavior. A browser test that only opens a page cannot prove a payment or state transition persisted correctly.

Choose representative normal, denied, boundary, repeated, concurrent, interrupted, and recovery cases based on the actual risk. Include regression tests for confirmed defects when they add durable confidence. Avoid exhaustive combinations that do not represent reachable states.

Define release evidence separately from test authoring: the exact candidate, environment, data setup, commands or cases run, results, and limitations. If time is constrained, prioritize by harm and disclose the untested risk. The release owner decides whether to accept that risk; QA does not manufacture confidence to meet a date.

## Decision Rules

- If a risk can be checked reliably in a lower layer, prefer it over a fragile E2E test.
- If a high-impact scenario lacks an oracle, resolve expected behavior before claiming coverage.

## Validation

- Does each material risk have a test or explicit acceptance of missing coverage?
- Are blocked and manual checks included in the plan?

## Common Failure Modes

- Coverage percentage substitutes for confidence: map risks.
- Testing everything equally: prioritize meaningful failure.

## Escalation and Collaboration

Product Manager supplies acceptance; engineers supply test seams; Security supplies abuse risks; release owner accepts gaps.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
