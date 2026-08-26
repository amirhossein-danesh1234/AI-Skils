# solution-strategy

[Scientific Problem Solver](README.md) / [University domain](../../README.md)

## Scientific Aim

Choose an analytic, numerical, experimental or hybrid route appropriate to the problem.

## Entry Conditions

A formulated scientific problem needs a justified route among analytic, numerical, experimental or hybrid methods.

## Modeling Boundary

Use after formulation; method preference cannot replace a fit-to-question comparison.

## Required Scientific Context

Well-posed formulation/model, target precision, scales/regimes, data and computational/experimental resources, deadline, safety/ethics and candidate methods.

## Scientific Workflow

1. Classify equations/question by linearity, dimensionality, stochasticity, stiffness, data availability and relevant symmetries/conservation.
2. Compare analytic simplification, numerical computation, experiment/observation and hybrid routes on assumptions, error control, cost and what each can establish.
3. Choose a staged route: establish baseline or solvable limit, execute the least costly discriminating method, then increase fidelity only if needed.
4. Define inputs, conditions, error budget, checkpoints, fallback and validation before calculation or data collection begins.

## Method Decision Table

Analytic methods expose dependence but may require strong simplification; numerical methods trade exactness for controlled computation; experiments observe reality but include measurement/confounding limits. Select by question and evidence—not prestige.

## Model and Method Rules

- A method must be capable of resolving the required scale and precision.
- If two methods have different biases, use agreement/disagreement as information rather than choosing post hoc.

## Scientific Deliverable

Strategy memo with problem classification, method comparison, selected stages, resources, error budget, validation, fallback and stop criteria.

## Validation Gates

- The selected route addresses the target and its boundary/initial conditions.
- Risks, ethics and safety requirements are identified before execution.

## Modeling Failure Modes

- **Jumping to simulation because available:** compare analytic scales first.
- **Experiment proposed when observation cannot distinguish hypotheses:** redesign measurement.

## Handoffs

Approximation reduces complexity; Numerical Methods selects algorithms; Methodology Design handles formal studies.
