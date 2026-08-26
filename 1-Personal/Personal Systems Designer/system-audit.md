# system-audit

[Personal Systems Designer](README.md) / [Personal domain](../../README.md)

## Purpose

Find where an existing personal system loses information, time or trust.

## Activate When

An existing personal system feels burdensome, unreliable or overdue for evidence-based review.

## Do Not Use When

Audit before redesign; complexity and maintenance are costs.

## Required Context

**Needed**

System purpose, users, components, current rules, workload, failures, maintenance time, metrics/proxies and constraints.

**Can be deferred or bounded**

A redesign proposal waits until actual failure and value are understood.

## Workflow

1. Restate the outcome the system must support and identify current sources of truth, handoffs, queues and recurring maintenance.
2. Sample real successes and failures. Measure capture/retrieval/completion reliability, delay, duplication, correction and upkeep at a proportionate level.
3. Distinguish rule failure, tool failure, adoption friction, excess scope and changed need. Identify controls that still earn their cost.
4. Recommend keep, simplify, repair, replace or retire; sequence reversible changes and define evidence for the next audit.

## Net System Value

Judge outcome reliability minus attention, maintenance, error and lock-in—not feature count. A system that is rarely needed may be acceptable if cheap and safe; an elegant system that demands constant grooming may not be.

## Decision Rules

- Fix the smallest material constraint before redesigning the architecture.
- Preserve working data and user habits unless the expected gain justifies migration risk.

## Output Contract

Audit with purpose, current map, observed evidence, burden, root causes, keep/change/retire decisions, staged actions and measures.

## Quality Gates

- Recommendations trace to observed failure or explicit changed need.
- Migration, privacy and rollback risks are addressed before tool changes.

## Failure Modes

- **Blaming inconsistency without measuring system friction:** inspect design.
- **New tool proposed as diagnosis:** identify required behavior first.

## Handoffs

Workflow/Task/File/PKM specialists redesign the relevant layer; Automation review tests lifecycle value.
