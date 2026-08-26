# Data Flow Design

Context: [Software Architect](README.md).

## Purpose

Specify how data moves, changes, and remains trustworthy across components.

## Activate When

A system has unclear ingestion, transformation, propagation, or retention behavior.

## Do Not Use When

Database schema design owns physical representation; this skill owns cross-component movement.

## Required Context

**Needed:** Sources, consumers, ownership, transformations, and freshness/consistency needs.

**Can be deferred or bounded:** Physical schemas can follow logical flows; sensitive-data destination and deletion obligations cannot.

## Workflow

1. Trace each critical datum from source through transformations to consumers.
2. Define authority, schema, identity, ordering, and acceptable freshness at every boundary.
3. Specify validation, deduplication, replay, backpressure, and partial-failure handling.
4. Review sensitive-data exposure, deletion propagation, and reconciliation between systems.

## Event Lifecycle

For an event, trace production, delivery, deduplication, ordering, replay, and consumer state. Record schema version, event time versus processing time, late arrival, and deletion propagation. If an event triggers a side effect, separate replay for rebuilding data from replay that would send or charge again.

## Decision Rules

- If a consumer requires stronger freshness than the pipeline guarantees, change the contract or architecture.
- If replay repeats side effects, add idempotency or a controlled reconciliation path.

## Output Contract

Flow map with provenance, contracts, timing, delivery semantics, failure handling, retention, and observability.

## Quality Gates

- Can missing, duplicated, delayed, and out-of-order data be detected and handled?
- Are derived values traceable to their source and transformation version?
- Recovery/replay does not silently repeat external effects or resurrect deleted private data.

## Failure Modes

- Arrows hide semantics: label timing and guarantees.
- Deletion stops at one system: trace downstream copies.

## Handoffs

Database Engineer validates integrity; Backend Engineer implements contracts; Security and DevOps review exposure and observation.
