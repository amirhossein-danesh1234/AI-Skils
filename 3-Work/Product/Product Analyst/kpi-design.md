# KPI Design

Context: [Product Analyst](README.md).

## Purpose

Select a small set of product measures that guide a specific decision.

## Activate When

A team needs useful outcomes and guardrails rather than a dashboard of everything.

## Do Not Use When

Do not define success as whichever metric is easiest to increase.

## Required Context

**Needed:** Decision owner, product outcome, value mechanism, and available observation points.

**Can be deferred or bounded:** Targets may remain provisional until baseline evidence exists; metric contracts and action ownership cannot.

## Workflow

1. Map the intended user outcome to a plausible product value mechanism.
2. Choose a primary outcome and a few explanatory drivers, not competing primary goals.
3. Add guardrails for harm, quality, cost, and underserved segments.
4. Specify what decisions a change in each measure triggers and validate measurement feasibility.

## Metric-to-Action Test

For each candidate KPI, write one plausible increase that is bad for the user and one decrease that is benign. Use these counterexamples to add a guardrail or reject the metric. Keep diagnostic drivers separate from the outcome so optimizing a proxy cannot silently replace the goal.

## Decision Rules

- If a metric can rise while user value deteriorates, add a guardrail or choose a better measure.
- If data is not trustworthy, define instrumentation work before targets.

## Output Contract

KPI set with outcome, drivers, guardrails, definitions, owners, review cadence, and action thresholds.

## Quality Gates

- Does each KPI support an actual decision and have a stable contract?
- Are targets grounded in baseline or explicitly provisional?
- Every selected KPI has a decision it can change and a misuse guardrail.

## Failure Modes

- Vanity metrics mistaken for outcomes: tie to behavior and value.
- Too many KPIs dilute accountability: keep decision ownership clear.

## Handoffs

Product Strategist supplies objectives; Product Manager owns actions; engineers validate measurement availability.
