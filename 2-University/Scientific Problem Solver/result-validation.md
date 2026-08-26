# result-validation

[Scientific Problem Solver](README.md) / [University domain](../../README.md)

## Scientific Aim

Test a scientific result against independent checks, data and its validity envelope.

## Entry Conditions

A scientific prediction, estimate, simulation or analytic result needs evidence beyond internal calculation.

## Modeling Boundary

Agreement with one check does not validate all assumptions or establish causality.

## Required Scientific Context

Question/model, result with units, assumptions/conditions, input provenance, uncertainty, comparison data or benchmark and intended use.

## Scientific Workflow

1. Verify reproducibility of the computation and audit units, signs, balances, conservation, bounds and boundary/initial conditions.
2. Test limiting cases, scale, sensitivity and convergence/robustness to discretization, parameters or plausible alternative assumptions.
3. Compare with independent analytic cases, observations, experiments or methods, accounting for measurement and model uncertainty.
4. Classify validation scope: supported within range, conditionally supported, contradicted or unresolved; identify next discriminating test.

## Validation Ladder

Separate code verification (solving equations correctly), solution verification (mathematical/numerical checks) and model validation (agreement with relevant reality). Good code cannot validate a wrong model.

## Model and Method Rules

- Do not tune against the same evidence and call it independent validation.
- Agreement within uncertainty is not proof of mechanism or general validity.

## Scientific Deliverable

Validation report with check matrix, data/provenance, sensitivity/convergence, discrepancy analysis, validity envelope, verdict and next test.

## Validation Gates

- At least one check is independent of the original route.
- The verdict is limited to tested regimes and intended use.

## Modeling Failure Modes

- **Visual curve agreement without residual/uncertainty:** quantify comparison.
- **One benchmark generalized everywhere:** map the envelope.

## Handoffs

Math/Physics Verification checks formal work; Researcher evaluates empirical evidence; safety-critical use requires domain qualification.
