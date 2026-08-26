# Data Analysis

Context: [Data-Analyst](README.md).

## Purpose

Answer a bounded question through a reproducible data-to-conclusion chain.

## When to Use

A bounded question can be answered from available data and needs a reproducible analytical result.

## Boundary

Domain owners define meaning and actions.

## Inputs

Question and decision use, permitted dataset, source/version, schema, row grain, units, coverage and needed output.

## Method

1. Translate the question into an estimand or descriptive quantity before inspecting attractive patterns. Confirm population, unit of analysis, comparison, horizon and which domain meanings require an owner.
2. Profile coverage, missingness, duplicate keys, impossible values and join cardinality. Reconcile input totals and understand what the collection process cannot observe.
3. Preserve raw data; create a reproducible transformation and analysis path. Use a small hand-checkable subset to test denominator, grouping, joins and time boundaries before scaling.
4. Summarize distributions and relevant segments, then apply inference only when design and assumptions support it. Separate exploratory findings from prespecified tests.
5. Trace each reported result back through definition, transformations and source. State the strongest supported interpretation, what remains uncertain and which decision it can inform.

## Analysis Boundary

Rows are not automatically independent observations or members of the target population. Joining a one-to-many table can multiply both apparent sample size and totals. A complete-looking dataset may omit unobserved failures or nonrespondents. If these gaps block the intended inference, deliver a quality/coverage diagnosis or a bounded descriptive result instead of a misleading overall answer.

## Output

Reproducible analysis with data version, definitions, reconciliation, result tables, uncertainty and decision-relevant limitations.

## Quality Checks

- At least one independent/manual check agrees on a material result and edge case.
- No domain-specific KPI target, causal story or action approval is inferred merely from a numeric pattern.

## Handoffs

Load [data-cleaning](data-cleaning.md), [statistical-reasoning](statistical-reasoning.md) or another focused skill only for a material bottleneck; domain analysts interpret professional significance.
