# numerical-methods

[Mathematics Tutor](README.md) / [University domain](../../README.md)

## Mathematical Goal

Select and assess a numerical method with stability, convergence and error awareness.

## Use This For

A mathematical problem needs a computational approximation and a justified method choice.

## Validity Boundary

Numerical agreement is evidence about computation, not a substitute for proof.

## Definitions and Preconditions

Problem class, domain/conditions, data scale and conditioning, accuracy/tolerance, cost limits, available libraries/precision and need for guarantees.

## Reasoning Protocol

1. Classify the problem and inspect existence, uniqueness, smoothness, conditioning, stiffness/sparsity or structure relevant to method behavior.
2. Compare candidate methods on assumptions, convergence order, stability region, robustness, memory/cost and available error control.
3. Specify discretization/initialization, stopping criterion, precision and diagnostics. Use a trusted implementation when appropriate and record version/settings.
4. Validate against an analytic case, refinement study, residual/backward error, invariant or independent method; report numerical and model error separately.

## Error Budget

Separate truncation/discretization, iteration, roundoff, data and modeling error. A small residual may coexist with large forward error in an ill-conditioned problem; convergence of iterates is not automatically convergence to the desired solution.

## Validity Rules

- Choose tolerance from the question and conditioning, not arbitrary decimal display.
- Never call numerical agreement a proof of a universal mathematical claim.

## Mathematical Output

Method decision with assumptions, alternatives, complexity, algorithm/settings, convergence/stability/error analysis, validation and limitations.

## Independent Checks

- The method’s hypotheses match the problem and boundary/initial conditions.
- Accuracy claims are supported by an error estimate or convergence evidence.

## Logical Failure Modes

- **Highest formal order chosen automatically:** account for stability, smoothness and cost.
- **One grid/seed/run accepted:** perform an independent or refinement check.

## Handoffs

CS Tutor supports implementation; Scientific Problem Solver chooses analytic versus numerical strategy; Proof Analysis handles formal claims.
