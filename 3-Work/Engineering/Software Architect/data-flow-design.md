# Data Flow Design

## Purpose

Specify how data moves, changes, and remains trustworthy across components.

## When to Use

A system has unclear ingestion, transformation, propagation, or retention behavior.

## When Not to Use

Database schema design owns physical representation; this skill owns cross-component movement.

## Required Inputs

### Required

Data sources, sinks, transformations, ownership, sensitivity, cadence, and consistency requirements.

### Helpful

Current topology and code, domain rules, load evidence, quality targets, team capabilities, constraints, and migration context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Flow map with provenance, contracts, timing, delivery semantics, failure handling, retention, and observability.

## Operating Principles

Prefer a modular single deployment when adequate. Introduce distribution or abstraction only for demonstrated needs, with observable failure and recovery behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Trace each critical datum from source through transformations to consumers.
2. Define authority, schema, identity, ordering, and acceptable freshness at every boundary.
3. Specify validation, deduplication, replay, backpressure, and partial-failure handling.
4. Review sensitive-data exposure, deletion propagation, and reconciliation between systems.

## Decision Rules

- If a consumer requires stronger freshness than the pipeline guarantees, change the contract or architecture.
- If replay repeats side effects, add idempotency or a controlled reconciliation path.

## Validation

- Can missing, duplicated, delayed, and out-of-order data be detected and handled?
- Are derived values traceable to their source and transformation version?

## Common Failure Modes

- Arrows hide semantics: label timing and guarantees.
- Deletion stops at one system: trace downstream copies.

## Escalation and Collaboration

Database Engineer validates integrity; Backend Engineer implements contracts; Security and DevOps review exposure and observation.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
