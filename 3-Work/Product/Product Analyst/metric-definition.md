# Metric Definition

Context: [Product Analyst](README.md).

## Purpose

Specify a product metric so independent calculations agree.

## Activate When

A decision uses an ambiguous measure or instrumentation is being designed.

## Do Not Use When

KPI design selects a decision system; this skill defines one measure precisely.

## Required Context

**Needed:** Metric meaning, eligible entity, source events, and time boundaries.

**Can be deferred or bounded:** If source access is absent, deliver a proposed contract and test fixtures, not a measured value.

## Workflow

1. Inspect raw events and confirm what each event actually records.
2. Define entity grain, deduplication, identity stitching, time zone, and late-arrival treatment.
3. Specify numerator and denominator from the same eligible population and observation window.
4. Calculate examples and edge cases, then reconcile against independent totals.

## Executable Examples

Include tiny hand-calculated fixtures for duplicate events, late arrivals, zero denominator, changed identity, and a boundary timestamp. Specify event time versus processing time and the backfill/revision policy. Version a definition change rather than splicing incompatible historical series.

## Decision Rules

- If the event represents an attempt rather than success, do not label it completion.
- If identity or eligibility changes, version the definition before comparing trends.

## Output Contract

Metric contract with grain, formula, denominator, eligibility, exclusions, time semantics, source, owner, and limitations.

## Quality Gates

- Can another analyst reproduce the value from the contract?
- Are zero denominators, duplicates, and incomplete windows handled?
- An independent calculation matches the fixtures and reconciles source counts.

## Failure Modes

- Metric name hides changing formula: version it.
- Incompatible numerator and denominator: align eligibility.

## Handoffs

Product Manager defines decision meaning; engineers confirm instrumentation; Financial Analyst owns financial metric treatment.
