# Backend Debugging

## Purpose

Identify the cause of a service failure through reproducible evidence.

## When to Use

An API, job, or business operation behaves incorrectly.

## When Not to Use

Diagnosis-only requests do not authorize fixes or production mutations.

## Required Inputs

### Required

Expected behavior, failing request or job, logs/traces, environment, recent changes, and data context.

### Helpful

Repository, runtime, business rules, contracts, data model, identity context, failure evidence, and deployment constraints.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Reproduction, causal explanation, authorized correction, and regression evidence.

## Operating Principles

Enforce invariants at the authoritative boundary, make retries safe, redact sensitive diagnostics, and verify persisted outcomes rather than status codes alone.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect deployment version, configuration, dependencies, and exact failing path.
2. Capture redacted evidence and reproduce with minimal safe data.
3. Test competing hypotheses across input validation, permissions, business logic, persistence, and integration boundaries.
4. Apply the smallest confirmed fix if authorized and verify the persisted outcome and adjacent failure paths.

## Decision Rules

- If the issue is environment or dependency availability, do not rewrite business logic to hide it.
- If evidence requires sensitive production data, use approved access and minimize disclosure.

## Validation

- Does the explanation account for both failing and non-failing cases?
- Does the regression test fail before and pass after the correction where practical?

## Common Failure Modes

- Speculative patches compound uncertainty: isolate cause.
- Status 200 mistaken for correctness: inspect state and side effects.

## Escalation and Collaboration

Database Engineer handles query or concurrency causes; DevOps handles deployment; QA retains reproduction.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
