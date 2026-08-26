# Backend Debugging

Context: [Backend Engineer](README.md).

## Purpose

Identify the cause of a service failure through reproducible evidence.

## Activate When

An API, job, or business operation behaves incorrectly.

## Do Not Use When

Diagnosis-only requests do not authorize fixes or production mutations.

## Required Context

**Needed:** Failure evidence, expected effect, runtime/version, and scoped data context.

**Can be deferred or bounded:** If reproduction needs protected production data, use approved minimized evidence or return the access dependency.

## Workflow

1. Inspect deployment version, configuration, dependencies, and exact failing path.
2. Capture redacted evidence and reproduce with minimal safe data.
3. Test competing hypotheses across input validation, permissions, business logic, persistence, and integration boundaries.
4. Apply the smallest confirmed fix if authorized and verify the persisted outcome and adjacent failure paths.

## Causal Boundary Trace

Correlate a request or job across validation, permission, transaction, external call, and acknowledgment. Distinguish an absent operation from a completed effect with a lost response. Change one confirmed mechanism; preserve the failing example as a regression instead of masking it with broad exception handling.

## Decision Rules

- If the issue is environment or dependency availability, do not rewrite business logic to hide it.
- If evidence requires sensitive production data, use approved access and minimize disclosure.

## Output Contract

Reproduction, causal explanation, authorized correction, and regression evidence.

## Quality Gates

- Does the explanation account for both failing and non-failing cases?
- Does the regression test fail before and pass after the correction where practical?
- The explanation accounts for actual persisted and external effects, not only the response code.

## Failure Modes

- Speculative patches compound uncertainty: isolate cause.
- Status 200 mistaken for correctness: inspect state and side effects.

## Handoffs

Database Engineer handles query or concurrency causes; DevOps handles deployment; QA retains reproduction.
