# E2E Test Planning

Context: [QA-Test Engineer](README.md).

## Purpose

Verify critical user journeys through the integrated application.

## Activate When

Cross-system behavior needs confidence that lower-layer tests cannot provide.

## Do Not Use When

Do not automate every visual detail or depend on uncontrolled external systems.

## Required Context

**Needed:** Critical journey, roles, acceptance oracle, environment, and controlled data.

**Can be deferred or bounded:** Visual details may use lower-layer checks; external effects must use a permitted sandbox or faithful substitute.

## Workflow

1. Choose journeys whose failure would materially harm users or business.
2. Prepare deterministic identities and data without relying on previous test runs.
3. Exercise real navigation, inputs, permissions, and persistence through supported interfaces.
4. Capture useful diagnostics and verify refresh or return behavior before cleanup.

## Journey Assertion

Exercise the user action through the UI and verify authoritative persistence after refresh or return. Avoid fixed sleeps when an observable state can signal readiness. Give each test independent setup/cleanup and diagnostic artifacts that distinguish product failure from fixture or environment failure.

## Decision Rules

- If a test can be replaced by a stable lower-layer check without losing confidence, move it down.
- If a test fails intermittently, diagnose the cause rather than hiding it with unlimited retries.

## Output Contract

Small E2E suite or plan with setup, user actions, authoritative outcomes, cleanup, and failure diagnostics.

## Quality Gates

- Can the journey finish from a clean state and retain its outcome?
- Are failures distinguishable from environment or fixture problems?
- The suite proves the business outcome rather than only successful navigation or a visible toast.

## Failure Modes

- Brittle selectors follow styling: target stable semantics.
- Only page loads checked: verify the domain outcome.

## Handoffs

Frontend and Backend Engineers provide stable behavior; Product Manager confirms critical journeys; DevOps maintains test environment.
