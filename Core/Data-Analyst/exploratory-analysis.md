# Exploratory Analysis

Context: [Data-Analyst](README.md).

## Purpose

Explore distributions, segments, funnels, cohorts and anomalies.

## When to Use

The shape, coverage or relationships in a dataset are not yet understood.

## Boundary

Exploration proposes hypotheses; it does not confirm causality.

## Inputs

Question, dataset/grain, collection changes, metric definitions, plausible segments and time coverage.

## Method

1. Inspect counts, missingness and distributions before associations. Use mean/median and spread appropriate to shape; show tails and denominators rather than a single average.
2. Compare prespecified or meaningful segments with their sample sizes and exposure. Check whether aggregate trends reverse within groups and whether composition changes explain the aggregate.
3. For sequential events, build a funnel with explicit eligibility/order/time limits. For cohorts, align entry and follow-up maturity; separate within-cohort change from changing cohort mix.
4. Examine anomalies against seasonality, collection changes, backfills and known context. A threshold crossing identifies a case to investigate, not a cause or automatic bad record.
5. Record explored cuts and candidate hypotheses. Reserve fresh data or a valid confirmatory design for claims discovered during exploration.

## Exploration Without Fishing

Searching many cuts makes striking patterns likely even without a stable effect. Preserve null and contrary findings and avoid presenting a selected subgroup as a prespecified test. Where cohorts or segments overlap, do not add their counts as independent groups. Apparent funnel loss can be delayed completion or missing instrumentation; reconcile before proposing a mechanism.

## Output

Compact distribution/segment/cohort findings, anomalies, data limitations and ranked hypotheses with next discriminating checks.

## Quality Checks

- Each pattern includes its denominator, window and collection caveats.
- No causal conclusion or precise forecast is promoted from an exploratory correlation alone.

## Handoffs

Use [data-visualization](data-visualization.md) for faithful displays and [hypothesis-generation](../Problem-Solver/hypothesis-generation.md) for testable mechanisms.
