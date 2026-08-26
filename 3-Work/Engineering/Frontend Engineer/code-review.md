# Frontend Engineer — Code Review

Context: [Frontend Engineer](README.md).

## Purpose

Review frontend changes for observable correctness, maintainability, and user impact.

## Activate When

A frontend diff is ready for review or a risky change needs scrutiny.

## Do Not Use When

Do not rewrite style preferences as defects or claim tests ran when only inspected.

## Required Context

**Needed:** Diff, expected behavior, callers, and relevant runtime conventions.

**Can be deferred or bounded:** Execution may be unavailable; report static reasoning separately from tests actually run.

## Workflow

1. Read the changed behavior and its callers before judging local code.
2. Trace state transitions, effects, async races, rendering, accessibility, and error paths.
3. Check tests against meaningful user behavior and identify missing high-risk cases.
4. Report only supported issues, separating confirmed defects, questions, and optional improvements.

## Reachability First

Trace the changed component through realistic consumers, events, and async ordering. Report a defect only with the triggering state and consequence; distinguish an optional refactor. For shared components, inspect a contrasting consumer to avoid a local fix that breaks another valid use.

## Decision Rules

- If a concern cannot produce a plausible failure or maintenance consequence, do not elevate it to a blocker.
- If a change touches shared components, inspect representative consumers.

## Output Contract

Prioritized actionable findings with file location, failure scenario, impact, and suggested correction.

## Quality Gates

- Can each finding be reproduced or demonstrated from the code path?
- Are severity and remediation proportional to user impact?
- Every actionable finding includes a reachable failure and appropriately scoped remedy.

## Failure Modes

- Style debate masks defect risk: prioritize correctness.
- Review summary implies execution: distinguish inspected from run checks.

## Handoffs

Consult UX for behavior, Backend Engineer for contracts, and Security for browser trust issues.
