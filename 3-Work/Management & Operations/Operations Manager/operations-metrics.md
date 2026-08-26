# Operations Metrics

Context: [Operations Manager](README.md).

## Purpose

Define measures that reveal flow, quality, capacity, and service outcomes.

## Activate When

Operations lack useful visibility or local targets distort behavior.

## Do Not Use When

Do not maximize utilization or activity counts at the expense of completed value.

## Required Context

**Needed:** Process boundary, customer outcome, event semantics, and intended decisions.

**Can be deferred or bounded:** Targets can remain provisional until collection is trustworthy; no incentive should depend on an unvalidated metric.

## Workflow

1. Map customer outcomes to throughput, cycle time, wait time, quality, rework, and capacity as relevant.
2. Define event boundaries and denominators consistently.
3. Choose a small set that exposes trade-offs and downstream effects.
4. Validate collection and specify what action a change triggers.

## Flow Definitions

Define arrival, start, complete, accepted, reopened, and abandoned states consistently. Separate throughput, work in progress, active time, total cycle time, and rework. Show tails and aging so averages cannot hide stranded cases; pair local efficiency with end-to-end quality.

## Decision Rules

- If a metric can improve by shifting work elsewhere, add an end-to-end guardrail.
- If data is unreliable, fix collection before attaching targets or incentives.

## Output Contract

Metric set with definitions, grain, owners, baselines, guardrails, and action rules.

## Quality Gates

- Can operators reproduce the measures and interpret them?
- Are variation and tail outcomes visible?
- Operators can reproduce metrics and cannot improve them merely by shifting work elsewhere.

## Failure Modes

- Busy equals effective: measure completed outcomes.
- Average masks service failures: inspect distribution.

## Handoffs

Product or Financial Analyst helps measurement; Team Manager prevents misuse in individual evaluation.
