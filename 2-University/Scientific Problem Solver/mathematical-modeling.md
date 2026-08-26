# mathematical-modeling

[Scientific Problem Solver](README.md) / [University domain](../../README.md)

## Scientific Aim

Translate a scientific question into variables, relations, conditions and testable outputs.

## Entry Conditions

A scientific question must be represented in equations or computable relations.

## Modeling Boundary

The model is a representation under assumptions, not observed truth.

## Required Scientific Context

Question/observable, system boundary, scales, variables/parameters, observations, candidate mechanisms, constraints, initial/boundary conditions and required fidelity.

## Scientific Workflow

1. Define the target output and system boundary; distinguish state variables, controls, parameters, observables and nuisance factors.
2. Choose governing balance, stochastic relation, geometric constraint or empirical model and map each term to a mechanism/assumption.
3. Specify initial/boundary conditions, parameter provenance, identifiability and the domain where the model is expected to hold.
4. Check dimensions and well-posedness, then propose calibration and validation data distinct where feasible; compare a simpler alternative.

## Model Card

Record purpose, equations, assumptions, parameter sources, conditions, outputs, validity envelope, uncertainty and known failure modes. The same equations may be predictive, explanatory or descriptive depending on evidence and use.

## Model and Method Rules

- Do not add parameters that available data cannot identify without priors/constraints.
- Prefer a simpler model when extra fidelity cannot affect the target within required precision.

## Scientific Deliverable

Mathematical model with variable table, equations/mechanisms, conditions, parameters/provenance, assumptions, solution route, calibration/validation and validity.

## Validation Gates

- The model is dimensionally coherent and sufficiently conditioned to address the target.
- Observed facts and modeling assumptions remain distinct.

## Modeling Failure Modes

- **Boundary conditions omitted:** model remains underdetermined.
- **Fit quality treated as mechanism proof:** separate prediction and explanation.

## Handoffs

Problem Formulation sets target; Solution Strategy chooses method; Researcher evaluates empirical support.
