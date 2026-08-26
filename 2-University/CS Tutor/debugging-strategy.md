# debugging-strategy

[CS Tutor](README.md) / [University domain](../../README.md)

## Learning Goal

Isolate a defect or misconception through hypotheses and discriminating tests.

## Activate For

A learner’s program or algorithm behaves unexpectedly and the cause is unknown.

## Educational Boundary

Do not randomly edit code or silently turn an educational exercise into production repair.

## Program or Problem Context

Expected versus observed behavior, minimal code, language/version, exact input, output/error, reproducibility, recent changes and learner hypothesis.

## Reasoning Lab

1. Make the failure reproducible and reduce it to a minimal case while preserving the symptom. Verify the expected behavior from specification.
2. Locate the first divergent state using traces, assertions, logging or debugger inspection—not the final visible symptom alone.
3. Form competing hypotheses and choose the smallest test whose outcomes discriminate them; change one causal factor at a time.
4. Apply the narrow fix, rerun the failing case and related boundaries, then explain the misconception and add a regression test or reasoning check.

## Hypothesis Table

For each hypothesis record predicted observation, discriminating test and result. A code edit is not a diagnostic test if several mechanisms change simultaneously. Tool output is evidence, not explanation.

## Correctness and Learning Rules

- Preserve the failing example before editing.
- Stop random retries and broad rewrites once a smaller discriminating test is possible.

## Teaching Deliverable

Debugging record with reproduction, first divergence, hypotheses/tests, root cause, minimal correction, regression cases and learner explanation.

## Correctness Checks

- The fix addresses the earliest causal defect and does not merely hide the symptom.
- Tests include the original failure and at least one adjacent edge case.

## Learning Failure Patterns

- **Guess-and-edit cycle:** return to observation and hypothesis.
- **Error message interpreted without language/runtime context:** reproduce exact environment.

## Handoffs

Code Tracing isolates state; Solution Verification broadens tests; Work engineers own production incidents and deployment.
