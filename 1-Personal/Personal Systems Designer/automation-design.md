# automation-design

[Personal Systems Designer](README.md) / [Personal domain](../../README.md)

## Purpose

Decide whether deterministic automation saves enough recurring friction to justify ownership.

## Activate When

A stable repetitive personal workflow might justify deterministic or tool-driven automation.

## Do Not Use When

Does not automate rare, unstable or consequential judgment by default.

## Required Context

**Needed**

Current steps, frequency/volume, manual time/errors, data and permissions, failure impact, implementation/maintenance estimates and horizon.

**Can be deferred or bounded**

Tool selection can wait until the value and control model pass.

## Workflow

1. Observe and simplify the manual workflow first. Remove unnecessary steps before encoding them.
2. Estimate horizon benefit using realistic frequency and saved effort, then subtract build, monitoring, repair, migration and learning costs.
3. Classify permissions and failure modes. Design preview, approval, idempotence, backups, logs, rollback and a manual fallback proportional to consequence.
4. Pilot on reversible low-risk cases; compare actual savings and maintenance. Scale, keep manual or retire using a defined threshold.

## Maintenance-Adjusted Value

Break-even is not only build time divided by minutes saved. Include expected failure loss, attention to monitoring, platform churn and the value of a reliable manual path. A small recurring task can rationally remain manual.

## Decision Rules

- Do not automate a changing or poorly understood process.
- Any action that sends, purchases, deletes, publishes or changes access defaults to preview/approval unless explicitly authorized and safely bounded.

## Output Contract

Automation decision with baseline, benefit/cost arithmetic, risks/permissions, control design, pilot, rollback, fallback and maintenance/retirement rule.

## Quality Gates

- Assumptions and horizon are explicit and sensitivity-tested.
- Recovery from partial failure is specified and tested where practical.

## Failure Modes

- **Ignoring maintenance makes automation appear free:** include lifecycle cost.
- **Automating clutter accelerates waste:** simplify first.

## Handoffs

Workflow Design stabilizes the process; AI Workflow Design handles probabilistic steps; System Audit checks continued value.
