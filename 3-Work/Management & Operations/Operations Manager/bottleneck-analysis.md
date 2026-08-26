# Bottleneck Analysis

Context: [Operations Manager](README.md).

## Purpose

Identify the constraint that limits completed throughput or service time.

## Activate When

Queues grow or local improvements do not improve outcomes.

## Do Not Use When

Do not equate the busiest person or longest task with the system bottleneck automatically.

## Required Context

**Needed:** Flow samples, queue/arrival/completion evidence, variability, and effective capacity.

**Can be deferred or bounded:** A long queue suggests but does not prove the constraint; test a mechanism before adding resources.

## Workflow

1. Inspect where work accumulates and how demand varies over time.
2. Compare effective capacity and completion rates across the full flow.
3. Test whether relieving the suspected constraint improves end-to-end output.
4. Consider rework, batching, approvals, and policy constraints before adding resources.

## Constraint Intervention

Separate active work, waiting for approval, batching, rework, and skill contention. Predict what should change if the suspected constraint is relieved, then measure completed throughput and quality. Stop upstream acceleration that only grows downstream queues and reassess if the constraint moves.

## Decision Rules

- If upstream acceleration only enlarges a downstream queue, stop optimizing that local step.
- If the constraint shifts after intervention, reassess rather than continuing the old fix.

## Output Contract

Constraint diagnosis with evidence, impact, candidate interventions, and measurement plan.

## Quality Gates

- Does evidence distinguish cause from queue symptoms?
- Are throughput and quality measured after the change?
- An intervention improves the system outcome, not only one local utilization metric.

## Failure Modes

- Utilization mistaken for bottleneck: inspect flow.
- More staff assumed solution: test policy and rework causes.

## Handoffs

Team Manager assesses capacity; [Process-optimization.md](process-optimization.md) tests improvements; Project Manager handles bounded dependency work.
