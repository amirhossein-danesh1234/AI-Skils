# Test Strategy

Context: [QA-Test Engineer](README.md).

## Purpose

Choose tests that provide useful confidence for the actual change and risk.

## Activate When

A feature, system, or release needs an evidence plan.

## Do Not Use When

Do not maximize test count or mandate every test layer for every change.

## Required Context

**Needed:** Change scope, critical outcomes/risks, architecture, and release constraints.

**Can be deferred or bounded:** Test plans can list missing environments; execution evidence must later state actual fidelity and coverage.

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

## Confidence Allocation

Prioritize tests by risk and the assumption they can falsify. Use the lowest reliable layer, adding E2E only for behavior that crosses real boundaries. For AI components, request AI Engineer behavioral evaluation in addition to software tests; mocks cannot establish model task reliability.

## Decision Rules

- If a risk can be checked reliably in a lower layer, prefer it over a fragile E2E test.
- If a high-impact scenario lacks an oracle, resolve expected behavior before claiming coverage.

## Output Contract

Risk-to-test strategy with layers, oracles, data, coverage, execution priorities, and exit criteria.

## Quality Gates

- Does each material risk have a test or explicit acceptance of missing coverage?
- Are blocked and manual checks included in the plan?
- Every material release risk has evidence or an explicit unresolved acceptance decision.

## Failure Modes

- Coverage percentage substitutes for confidence: map risks.
- Testing everything equally: prioritize meaningful failure.

## Handoffs

Product Manager supplies acceptance; engineers supply test seams; Security supplies abuse risks; release owner accepts gaps.
