# Regression Testing

Context: [QA-Test Engineer](README.md).

## Purpose

Check that a change preserves important existing behavior.

## Activate When

A fix, refactor, dependency update, or release could break prior capabilities.

## Do Not Use When

Do not rerun unrelated expensive tests without considering change impact, or claim unrun suites passed.

## Required Context

**Needed:** Change diff, affected contracts/consumers, prior defects, and available suites.

**Can be deferred or bounded:** A selected subset is acceptable when disclosed; it is not a full-suite pass.

## Workflow

1. Map changed code and contracts to affected consumers and historical failure patterns.
2. Select tests by impact and include an original defect reproduction when relevant.
3. Run in a controlled environment and separate failures, flakes, skips, and blocked checks.
4. Investigate regressions and rerun affected evidence after corrections.

## Change-to-Coverage

Map each changed behavior to direct tests and representative downstream consumers. Preserve the original defect trigger and add adjacent cases only when they protect plausible regressions. Track attempts separately from final results so retries cannot erase flakiness.

## Decision Rules

- If a shared contract changes, include representative downstream consumers.
- If the full suite is impractical, disclose the selection and uncovered risk rather than claiming full validation.

## Output Contract

Regression selection, executed results, gaps, failures, and risk assessment.

## Quality Gates

- Does evidence identify exact version, environment, and commands or cases?
- Are unresolved failures and skips explained?
- The report names candidate, environment, commands/cases, and passed/failed/skipped/blocked evidence accurately.

## Failure Modes

- Green subset described as full suite: report scope precisely.
- Repeated retries hide flakes: investigate reliability.

## Handoffs

Engineering owners fix regressions; [release-quality-review.md](release-quality-review.md) interprets overall readiness.
