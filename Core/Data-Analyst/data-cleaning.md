# Data Cleaning

Context: [Data-Analyst](README.md).

## Purpose

Resolve quality defects with reversible transformations and reconciliation.

## When to Use

Quality defects could alter an analysis and need traceable correction or explicit quarantine.

## Boundary

Do not silently alter the represented population.

## Inputs

Immutable raw data, schema/meaning, intended analysis, key constraints, collection process and permitted transformations.

## Method

1. Profile defect types by field and subgroup: missing, invalid, inconsistent, duplicate, out-of-range and unexpected category. Distinguish a recording error from a valid rare event.
2. Define correction rules before applying them. Normalize types, units and timestamps using known source conventions; quarantine ambiguous conversions rather than guessing.
3. Resolve duplicates at the intended entity/event grain. Specify key, version, ordering and survivor rule; repeated observations may be legitimate and must not be collapsed blindly.
4. Choose missing-value treatment from likely mechanism and intended inference. Retain missingness indicators where useful; do not assume zero or mean imputation is harmless.
5. Record transformations and rejected rows. Reconcile row counts, unique entities, totals and subgroup coverage before/after, including joins and filters; rerun the analysis under plausible alternative treatments.

## Reversibility and Selection

Keep raw data unchanged and record the lineage of each material correction. An outlier should not be removed because it spoils a result. Dropping incomplete rows can change the population; imputation adds assumptions, not observed evidence. If join cardinality is unexpected, stop the affected transformation and inspect keys rather than deduplicating the inflated output until totals look right.

## Output

Cleaned derivative, transformation log, defect/quarantine summary, reconciliations and sensitivity to unresolved choices.

## Quality Checks

- No deleted or imputed observation disappears from the coverage accounting.
- The same input and rules reproduce the same derivative; privacy-sensitive records are not exposed in diagnostic samples.

## Handoffs

[Metric-definition](metric-definition.md) establishes grain and eligibility; [statistical-reasoning](statistical-reasoning.md) assesses inferential consequences of missingness or selection.
