# Cohort Analysis

Context: [Product Analyst](README.md).

## Purpose

Compare groups with shared starting conditions across time or lifecycle age.

## Activate When

Aggregate trends hide differences between acquisition, launch, or behavior groups.

## Do Not Use When

Do not treat post-outcome segmentation as unbiased evidence of causality.

## Required Context

**Needed:** Entry event, entity grain, outcome, and dated observations.

**Can be deferred or bounded:** Without mature follow-up, report only observed ages; segment detail can wait until sample sizes support comparison.

## Workflow

1. Choose a cohort event that precedes the outcome and matches the decision.
2. Assign entities consistently and define treatment of repeat entry or migration.
3. Align lifecycle age and report incomplete periods explicitly.
4. Compare composition and external changes before attributing differences to product improvements.

## Cohort Construction

Build a small membership audit before aggregation: entity, entry time, cohort, observed age, outcome, and censoring reason. Treat an entity switching segment after entry consistently. Show both calendar-period and lifecycle-age views when a launch or seasonal event could explain the apparent difference.

## Decision Rules

- If a cohort is defined using future behavior, label selection bias and avoid causal claims.
- If groups are sparse, combine only when meaning remains coherent or report uncertainty.

## Output Contract

Cohort table or curves with definitions, sample sizes, maturity, composition, and interpretation.

## Quality Gates

- Can every entity’s assignment be reproduced?
- Are age, calendar effects, and acquisition mix separated?
- An immature cohort cannot contribute a fabricated zero for an unobserved period.

## Failure Modes

- Calendar and lifecycle time confused: label axes.
- Survivor-only data biases results: include eligible non-returners.

## Handoffs

Product Manager defines the decision; engineers validate identities; Market or Marketing specialists explain acquisition context.
