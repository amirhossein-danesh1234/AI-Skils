# order-of-magnitude-estimation

[Scientific Problem Solver](README.md) / [University domain](../../README.md)

## Scientific Aim

Estimate a scientific scale from dominant factors and defensible ranges.

## Entry Conditions

A scale, feasibility or plausibility question needs a fast defensible estimate.

## Modeling Boundary

Use for scale and feasibility, not false precision or safety-critical certification.

## Required Scientific Context

Target quantity and units, system scale, known reference values with provenance, dominant mechanisms, plausible ranges and acceptable precision.

## Scientific Workflow

1. Define the target scale and decompose it into count, rate, density, geometry or balance factors that can be estimated independently.
2. Choose central values and plausible low/high bounds, documenting sources or reasoning and avoiding correlated double counting.
3. Calculate in powers of ten or one-significant-figure ranges; identify the factors dominating uncertainty and result.
4. Cross-check through an independent decomposition, dimensional relation or known benchmark and state what decision the estimate can support.

## Fermi Range

Report an order/range, not decorative decimals. Sensitivity to a factor matters more than exact arithmetic; if the range crosses the decision threshold, gather better evidence rather than force a point estimate.

## Model and Method Rules

- Use current authoritative values when changing external quantities materially affect the estimate.
- Do not use a rough estimate as certification for safety-critical action.

## Scientific Deliverable

Estimate with decomposition, units, central/range assumptions, arithmetic, sensitivity drivers, independent check and decision implication.

## Validation Gates

- Units cancel to the target and orders of magnitude are arithmetically consistent.
- The uncertainty range reflects major unknown factors.

## Modeling Failure Modes

- **Many precise inputs create false confidence:** round to evidence quality.
- **Only one decomposition used:** seek an orthogonal benchmark.

## Handoffs

Researcher sources reference values; Dimensional Analysis checks form; qualified experts validate safety-critical uses.
