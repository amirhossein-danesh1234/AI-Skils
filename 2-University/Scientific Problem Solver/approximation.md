# approximation

[Scientific Problem Solver](README.md) / [University domain](../../README.md)

## Scientific Aim

Choose a simplification and quantify when its neglected effects remain acceptable.

## Entry Conditions

A scientific model is too complex and needs a controlled simplification.

## Modeling Boundary

An approximation is not a convenience phrase; its scale, error and validity range must be defensible.

## Required Scientific Context

Full or candidate model, target observable, characteristic scales, required accuracy, parameter ranges, relevant data and neglected-effect candidates.

## Scientific Workflow

1. Identify the output and tolerance, then nondimensionalize or compare characteristic term magnitudes.
2. Propose a simplification by neglecting, linearizing, averaging, decoupling or asymptotically expanding a specific effect.
3. Derive the reduced model and an error indicator or remainder estimate; state the parameter/regime that controls validity.
4. Validate against a solvable limit, fuller model, data or numerical comparison across the intended range and mark breakdown triggers.

## Controlled Simplification

Name the small/large dimensionless parameter and the order retained whenever possible. “Negligible” requires comparison to the target precision, not merely a small absolute number.

## Model and Method Rules

- Do not combine approximations without tracking their separate regimes and errors.
- Use the least simplifying assumption that achieves tractability and required precision.

## Scientific Deliverable

Approximation record with target/tolerance, scale comparison, reduced equations, controlling parameter, error estimate, validity range and validation.

## Validation Gates

- Neglected terms are dimensionally and quantitatively compared.
- The result states where and how the approximation fails.

## Modeling Failure Modes

- **Approximation chosen after seeing desired answer:** justify before fitting.
- **Small local error assumed globally small:** analyze accumulation/stability.

## Handoffs

Mathematical Modeling supplies full equations; Solution Strategy compares numerical alternatives; Result Validation tests outcomes.
