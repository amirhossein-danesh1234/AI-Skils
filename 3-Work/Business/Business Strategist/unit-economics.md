# Business Strategist — Unit Economics

Context: [Business Strategist](README.md).

## Purpose

Test whether a business-model unit can create sustainable contribution.

## Activate When

A strategy relies on scaling customers, orders, transactions, or another unit.

## Do Not Use When

[Financial Analyst unit-economics](../Financial%20Analyst/unit-economics.md) owns detailed calculation and reconciliation; this skill tests the business-model mechanism.

## Required Context

**Needed:** Economic unit, revenue mechanism, delivery/acquisition drivers, and lifecycle.

**Can be deferred or bounded:** Financial Analyst owns reconciled arithmetic; early drivers can remain bounded hypotheses.

## Workflow

1. Define the unit and when revenue and costs occur.
2. Map acquisition, fulfillment, support, returns, and retention mechanisms.
3. Identify which drivers improve or worsen with scale and which are merely assumed.
4. Request reconciled calculations and compare strategic levers to improve the unit.

## Scale Mechanism

Identify which cost or revenue driver would improve with scale and why. Separate fixed-cost spreading from changes in marginal contribution, and test whether support, returns, incentives, or concentration worsen the next unit. Request cohort-aware calculations rather than maintaining a competing financial model.

## Decision Rules

- If growth increases negative contribution, do not assume scale fixes it without a mechanism.
- If customer lifetime is unobserved, use bounded scenarios rather than unlimited lifetime value.

## Output Contract

Unit-economic hypothesis with drivers, break conditions, evidence gaps, and strategic implications.

## Quality Gates

- Is the unit consistent across revenue and cost assumptions?
- Are strategic conclusions robust to plausible driver changes?
- Strategic conclusions reference Financial Analyst’s validated calculation and expose unobserved lifetime assumptions.

## Failure Modes

- Gross margin called full unit economics: include relevant incremental costs.
- Forecast treated as observed proof: label evidence.

## Handoffs

Financial Analyst computes and reconciles the model; Product Analyst validates retention; Operations validates delivery costs.
