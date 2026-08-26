# Metric Definition

Context: [Data-Analyst](README.md).

## Purpose

Define grain, population, denominator, window and edge-case semantics.

## When to Use

A measure must be comparable across data sources, periods or decisions.

## Boundary

No product KPI strategy or financial accounting rule.

## Inputs

Construct to measure, population, events/records, identity rules, time basis, units and intended use.

## Method

1. Define the real-world construct separately from its observable proxy. Specify unit/grain, eligible population, numerator, denominator, aggregation and exclusions.
2. Define event versus processing time, time zone, observation window, lateness/backfill policy and maturity. Separate unknown, pending, ineligible and true zero.
3. For ratios, align numerator and denominator populations and periods. State whether aggregation is ratio-of-sums or mean-of-ratios and why; preserve component counts.
4. Test fixtures for duplicates, identity changes, denominator zero, late outcomes, boundary timestamps and missing values. For funnels/cohorts, define entry, ordered steps, re-entry and follow-up eligibility.
5. Version the definition and record changes in instrumentation or semantics. Reconcile old/new versions before joining them into a trend.

## Denominator Contract

A count of events cannot estimate the share of people affected without supported identity and an eligible-person denominator. Unequal observation time can make a younger cohort appear worse; show mature windows or an appropriate censoring method. A zero denominator is undefined, not a zero rate. Treat a target as comparable only after its definition matches.

## Output

Metric specification with formula, grain, population, time/identity policy, exclusions, fixtures and known proxy limitations.

## Quality Checks

- Another analyst can independently compute the same measure from the specification.
- Changes to denominator or maturity are visible rather than silently improving the result.

## Handoffs

Domain owners supply product, financial, academic or health meaning; [exploratory-analysis](exploratory-analysis.md) uses the definition without redefining it to fit findings.
