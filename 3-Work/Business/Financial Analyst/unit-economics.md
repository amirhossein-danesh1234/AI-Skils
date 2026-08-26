# Financial Analyst — Unit Economics

Context: [Financial Analyst](README.md).

## Purpose

Calculate reconciled economics for a defined customer, order, or transaction unit.

## Activate When

A pricing, growth, or operating decision depends on incremental value per unit.

## Do Not Use When

Business Strategist owns unit-economic hypotheses; this skill validates calculations and evidence.

## Required Context

**Needed:** Unit/population, revenue and relevant incremental costs, periods, and source records.

**Can be deferred or bounded:** Unobserved lifetime requires bounded scenarios; do not convert immature retention into a precise LTV.

## Workflow

1. Define the unit and align revenue and cost populations and periods.
2. Include fulfillment, processing, support, refunds, incentives, and other relevant incremental costs.
3. Separate observed contribution from lifetime estimates and acquisition allocations.
4. Test cohort variation, retention uncertainty, and scale effects on cash and margin.

## Unit Reconciliation

Reconcile unit totals to aggregate records, excluding internal transfers and aligning acquisition cohorts with outcomes. Include payment fees, support, incentives, returns, and fulfillment where relevant. Report contribution, acquisition cost, and payback with distinct definitions rather than one ambiguous profit-per-customer figure.

## Decision Rules

- If lifetime is not observed, report bounded scenarios rather than a precise unlimited LTV.
- If acquisition costs include different cohorts than revenue, reconcile before calculating payback.

## Output Contract

Unit model with contribution, acquisition/payback where relevant, lifecycle scenarios, sensitivity, and limitations.

## Quality Gates

- Can unit totals reconcile to aggregate records?
- Are denominators, retention, discounting, and cost inclusions explicit?
- The denominator and timing remain consistent across revenue, cost, retention, and acquisition calculations.

## Failure Modes

- Gross margin labeled unit profit: include relevant incremental cost.
- Average hides unprofitable cohorts: segment where meaningful.

## Handoffs

Product Analyst validates cohorts; Marketing and Sales supply acquisition costs; Business Strategist interprets viability.
