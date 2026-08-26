# Release Quality Review

Context: [QA-Test Engineer](README.md).

## Purpose

Translate actual test evidence into a transparent release-risk recommendation.

## Activate When

A release owner needs a go, hold, or conditional recommendation.

## Do Not Use When

QA does not accept business risk on behalf of the release owner or infer success from build completion.

## Required Context

**Needed:** Exact candidate, executed test evidence, acceptance, known defects, and release exposure.

**Can be deferred or bounded:** Missing evidence remains a gate or accepted risk; build success is not a substitute.

## Workflow

1. Confirm the tested artifact matches the release candidate and scope.
2. Review evidence for critical journeys, permissions, data integrity, recovery, and changed contracts.
3. Assess known defects by user impact, workaround, exposure, and detectability.
4. Recommend release, limited exposure, or hold with explicit conditions and owner acceptance.

## Evidence Reconciliation

Reconcile claimed results to the candidate and environment actually tested. Separate product readiness, technical test confidence, and operational rollout safety. For a conditional release, state audience limit, unresolved risk, detection/stop signal, and the real person authorized to accept it.

## Decision Rules

- If a critical invariant or security boundary is unverified or failing, recommend hold or remove affected exposure.
- If remaining risk is bounded and reversible, propose conditional rollout with monitoring and stop rules.

## Output Contract

Quality readout with coverage, pass/fail/skip/block counts, critical defects, residual risks, and recommendation.

## Quality Gates

- Are all claims backed by executed evidence or clearly labeled assessment?
- Are release gates, residual-risk owners, and untested areas visible?
- No failed or untested critical boundary is averaged away by a high overall pass count.

## Failure Modes

- No known bugs becomes proof of safety: report coverage limits.
- Skipped tests silently counted as pass: separate statuses.

## Handoffs

DevOps verifies rollout and recovery; Product Manager owns product readiness; authorized release owner decides.
