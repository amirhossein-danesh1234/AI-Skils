# Data Visualization

Context: [Data-Analyst](README.md).

## Purpose

Encode comparisons faithfully and expose scale and uncertainty.

## When to Use

A visual can materially clarify a supported comparison, distribution, relationship or sequence.

## Boundary

No decorative chart or unsupported visual persuasion.

## Inputs

Analytical question, validated data/definitions, audience, relevant uncertainty, display constraints and privacy limits.

## Method

1. Choose the comparison first: categories, time, distribution, relationship or composition. Use the simplest encoding that exposes it; a table may be better for a few exact values.
2. Make units, denominator, period, population and source visible. Use consistent scales for comparison; explain transformations and avoid area/volume encodings that exaggerate magnitude.
3. Represent missing periods and uncertainty honestly. Bars generally need a meaningful zero baseline; a restricted line-chart axis needs clear labeling and must not imply a larger practical change.
4. Use ordering, annotation and accessible contrast to direct attention to evidence, not decoration. Avoid dual axes or selective windows that manufacture agreement.
5. Reconcile plotted values to the analysis, inspect labels/legibility and test whether the title states a supported finding rather than a causal story.

## Visual Honesty

Counts and rates answer different questions; show exposure when it changes interpretation. A smoothed curve can hide sparse or irregular data, so expose points/sample support when material. Do not connect unavailable observations as if measured. If uncertainty prevents a clear rank, do not use visual ordering to imply certainty. Suppress or aggregate sensitive small groups according to actual privacy rules, not an invented universal cutoff.

## Output

One decision-useful chart or table with definitions, source, uncertainty and a concise supported reading.

## Quality Checks

- Visual and numerical conclusions agree; every highlighted difference has the right comparison basis.
- The chart remains interpretable without relying only on color or on an omitted footnote.

## Handoffs

[Insight-synthesis](insight-synthesis.md) interprets the pattern; domain owners decide what action the evidence warrants.
