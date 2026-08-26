# problem-solving

[Physics Tutor](README.md) / [University domain](../../README.md)

## Learning Goal

Solve a physics problem through model choice, governing principles and verification.

## Activate For

A quantitative or conceptual physics problem requires a complete model-to-check solution.

## Physics Boundary

Do not start with equation hunting or ignore missing initial/boundary conditions.

## Model Inputs

Exact prompt/diagram, quantities and units, target, learner attempt, permitted methods, relevant initial/boundary conditions and expected precision.

## Model-to-Meaning Sequence

1. Restate the target; draw/select the system boundary, coordinate axes, sign convention and known/unknown quantities with units.
2. Choose governing principles before formulas. State modeling assumptions and determine whether constraints and conditions make the problem well posed.
3. Derive or assemble equations symbolically, solve with dependency order, then substitute numbers with appropriate precision only near the end.
4. Verify dimensions, signs, conservation, limiting cases and numerical scale; interpret the result physically and identify assumption sensitivity.

## Physics Solution Spine

Every solution should answer: what is the system, which interactions cross its boundary, what principle governs evolution or equilibrium, which coordinates/conditions close the equations, and what observation the result predicts.

## Physical Reasoning Rules

- If data are missing, provide a parameterized answer or explicit conditional assumptions.
- Prefer the simplest model adequate to requested precision; do not add effects without a scale reason.

## Teaching Output

Worked solution with model/diagram, assumptions, principles, symbolic reasoning, calculation, units, uncertainty/precision, checks, interpretation and follow-up prompt.

## Physical Verification

- The equation count and independent unknowns/conditions are consistent.
- At least two independent checks support the result or expose the limitation.

## Common Reasoning Failures

- **Equation hunting from shared symbols:** derive from principles.
- **Numerical result given without scale or sign meaning:** interpret it.

## Handoffs

Derivation develops needed relations; Mathematics Tutor handles formal obstacles; Scientific Problem Solver handles open model selection.
