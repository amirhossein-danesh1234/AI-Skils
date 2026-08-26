# solution-verification

[Mathematics Tutor](README.md) / [University domain](../../README.md)

## Mathematical Goal

Check a mathematical result independently using substitution, bounds, structure or alternative reasoning.

## Use This For

A mathematical answer needs an independent correctness and completeness check.

## Validity Boundary

Verification does not excuse an invalid derivation when proof is required.

## Definitions and Preconditions

Original problem, candidate solution, domain/conditions, derivation or proof, required exactness and allowed computational tools.

## Reasoning Protocol

1. Check that the candidate satisfies the original statement, not only transformed equations, and list any excluded domain points.
2. Audit reversibility of transformations, branches, constants, boundary conditions and theorem assumptions.
3. Use independent checks appropriate to the object: substitution, differentiation/integration, residual, bounds, invariants, special cases, alternative representation or counterexample search.
4. Report correct/partially correct/incorrect/underdetermined, identify earliest issue and reconstruct only what the evidence justifies.

## Equivalence Audit

Mark every potentially lossy or solution-creating operation—division, squaring, roots/logs, inverse functions, differentiation/integration, limit/interchange, numerical rounding—and test candidates in the original problem.

## Validity Rules

- A decimal match supports only the tested case and precision.
- When an expression is equivalent only on a subdomain, state that subdomain in the verdict.

## Mathematical Output

Verification report with status, domain audit, independent checks, missing/extraneous cases, correction and residual uncertainty.

## Independent Checks

- All reported solutions pass the original conditions.
- Completeness is established or explicitly left unresolved.

## Logical Failure Modes

- **Repeating original algebra:** choose an orthogonal check.
- **Computer algebra output accepted without assumptions:** inspect conditions and branches.

## Handoffs

Problem Solving rebuilds the argument; Numerical Methods validates approximation; Proof Analysis handles theorem-level completeness.
