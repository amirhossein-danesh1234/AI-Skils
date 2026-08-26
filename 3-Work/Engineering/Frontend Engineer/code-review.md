# Code Review

## Purpose

Review frontend changes for observable correctness, maintainability, and user impact.

## When to Use

A frontend diff is ready for review or a risky change needs scrutiny.

## When Not to Use

Do not rewrite style preferences as defects or claim tests ran when only inspected.

## Required Inputs

### Required

Diff, requirements, surrounding components, API contracts, tests, and runtime context.

### Helpful

Repository instructions, approved UI and behavior, runtime versions, API contracts, existing tests, and supported devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Prioritized actionable findings with file location, failure scenario, impact, and suggested correction.

## Operating Principles

Follow existing conventions, keep state minimal, test realistic interactions, and distinguish compilation from verified user behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Read the changed behavior and its callers before judging local code.
2. Trace state transitions, effects, async races, rendering, accessibility, and error paths.
3. Check tests against meaningful user behavior and identify missing high-risk cases.
4. Report only supported issues, separating confirmed defects, questions, and optional improvements.

## Decision Rules

- If a concern cannot produce a plausible failure or maintenance consequence, do not elevate it to a blocker.
- If a change touches shared components, inspect representative consumers.

## Validation

- Can each finding be reproduced or demonstrated from the code path?
- Are severity and remediation proportional to user impact?

## Common Failure Modes

- Style debate masks defect risk: prioritize correctness.
- Review summary implies execution: distinguish inspected from run checks.

## Escalation and Collaboration

Consult UX for behavior, Backend Engineer for contracts, and Security for browser trust issues.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
