# Bug Reproduction

Context: [QA-Test Engineer](README.md).

## Purpose

Create a minimal, reliable account of a defect and its impact.

## Activate When

A reported failure cannot yet be reproduced or communicated clearly.

## Do Not Use When

Do not implement speculative fixes or expose sensitive production data in a bug report.

## Required Context

**Needed:** Reported difference, expected behavior source, version/environment, and safe evidence.

**Can be deferred or bounded:** An intermittent issue may remain unreproduced; retain frequency and conditions rather than marking resolved.

## Workflow

1. Verify the report against the current version and capture relevant environment details.
2. Reproduce with original context, then remove unnecessary steps and data.
3. Vary one factor at a time to identify boundary conditions and intermittent triggers.
4. Record reliable reproduction or explicitly state remaining uncertainty and next evidence needed.

## Minimal Failing Case

Reproduce the original environment first, then remove one dependency or step at a time. Record exact data state and timing needed without exposing personal data. Preserve a clean control case that succeeds; it helps distinguish the trigger from coincidental context.

## Decision Rules

- If the issue cannot be reproduced, do not call it resolved; preserve evidence and narrow the conditions.
- If expected behavior is disputed, route the requirement question separately from the technical symptom.

## Output Contract

Reproduction with prerequisites, steps, expected/actual results, frequency, impact, and sanitized evidence.

## Quality Gates

- Can another person reproduce from a clean relevant state?
- Are logs, screenshots, and identifiers sanitized but useful?
- Another tester can attempt the reproduction without hidden setup or an assumed expected result.

## Failure Modes

- Vague “does not work”: state the observed difference.
- Reproduction depends on hidden state: document or isolate it.

## Handoffs

Product Manager confirms expected behavior; engineers investigate cause; Security handles sensitive exposure.
