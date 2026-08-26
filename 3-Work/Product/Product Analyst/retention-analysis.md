# Retention Analysis

Context: [Product Analyst](README.md).

## Purpose

Measure whether customers return or continue receiving value on the product’s natural cadence.

## Activate When

A team needs to understand sustained use, churn, or reactivation.

## Do Not Use When

Do not use daily activity for products whose value naturally recurs monthly or episodically.

## Required Context

**Needed:** Entry/return value events, entity identity, observation horizon, and product cadence.

**Can be deferred or bounded:** Revenue retention can wait if billing data is unavailable; do not substitute activity retention for it.

## Workflow

1. Define the initial and return value events and distinguish user, account, and revenue retention.
2. Choose exact-period, rolling, or bounded retention to match the question and state the interpretation.
3. Handle censoring, reactivation, plan changes, and incomplete observation consistently.
4. Compare segments and investigate value loss using customer evidence.

## Retention Denominator

State whether retention means return in an exact interval, any later interval, or a bounded window. Keep initial cohort size, observed population, resurrected users, and churn rules visible. Test an account with several users and an intermittently used product to avoid treating account and user retention as interchangeable.

## Decision Rules

- If cohorts are not equally mature, compare only shared observed ages.
- If contractual lock-in sustains payment without use, report behavioral and commercial retention separately.

## Output Contract

Retention definition and curves, mature cohort comparisons, churn patterns, uncertainty, and product implications.

## Quality Gates

- Are denominators fixed and late observations handled correctly?
- Does the return event represent value rather than a trivial heartbeat?
- Reactivation and right-censoring have explicit treatment in the displayed curve.

## Failure Modes

- Immature cohorts appear to churn: handle censoring.
- Usage cadence mismatch: define meaningful return windows.

## Handoffs

Product Manager owns retention action; Sales supplies cancellation context; Financial Analyst owns revenue implications.
