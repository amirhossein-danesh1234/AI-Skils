# Model Selection

Context: [AI Engineer](README.md).

## Purpose

Select a model configuration using measured task performance under deployment constraints.

## Activate When

A production task needs an initial model or a current model may be replaced.

## Do Not Use When

Software Architect selects system structure; vendor rankings are not task-level evidence.

## Required Context

**Needed:** Task and evaluation cases, quality floor, data restrictions, deployment requirements, and candidate access.

**Can be deferred or bounded:** Public benchmarks can shortlist. Current prices, region availability, retention terms, limits, and pinned identifiers must be verified before commitment.

## Workflow

1. Apply hard gates for allowed data, licensing, hosting, modality, context, tool/structured-output support, and availability. Record exact model/version and configuration.
2. Run the same held-out tasks across candidates with task-appropriate prompts and comparable budgets. Keep tuning cases separate and count refusals, timeouts, invalid output, and abstention.
3. Measure success and critical failure by slice, repeated-run variation, end-to-end latency, and total cost per accepted task including fallback and review.
4. Inspect candidate-specific failures and portability costs. Choose the simplest configuration meeting all gates rather than averaging away a severe slice failure.
5. Stage the change with rollback to a known configuration and re-evaluate after material provider or task changes.

## Decision Rules

- If no model clears a critical gate, change task scope or keep the baseline; do not pick the highest average by default.
- If a floating alias can change behavior, monitor it and retain reproducible version records where supported.

## Output Contract

Candidate scorecard with hard-gate results, eval version, slice failures, latency/cost distributions, choice, and rollout conditions.

## Quality Gates

- Comparisons use the same task population and report all attempted runs.
- The deployment configuration matches what was evaluated.

## Failure Modes

- Leaderboard score substitutes for local evaluation.
- Token price hides retries and human review.

## Handoffs

evaluation-design owns rubric; Security verifies supplier/data constraints; DevOps verifies quotas and deployment; Financial Analyst validates material costs.
