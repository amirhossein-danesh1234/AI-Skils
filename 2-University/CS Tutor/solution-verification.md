# solution-verification

[CS Tutor](README.md) / [University domain](../../README.md)

## Learning Goal

Test a proposed algorithm or program against specification, invariants and edge cases.

## Activate For

A proposed algorithm, pseudocode or student program needs an independent check.

## Educational Boundary

Passing examples is not a correctness proof and cannot establish unspecified requirements.

## Program or Problem Context

Specification, constraints, solution/code, language semantics, claimed complexity/correctness and known tests.

## Reasoning Lab

1. Build a requirements checklist and identify algorithm state, invariant and termination condition independently of the author’s explanation.
2. Trace smallest, boundary, typical and adversarial inputs; generate cases targeted at assumptions, mutation, overflow, duplicates and empty structures.
3. Check correctness argument and complexity from code paths, including recursion depth, hidden operations and data-structure guarantees.
4. Classify findings, provide the smallest counterexample for defects, and suggest a correction plus regression/transfer tests without replacing learning unnecessarily.

## Test–Proof Boundary

Tests demonstrate failures and sample behavior. A finite exhaustive domain can be certified by complete enumeration; otherwise passing tests complements but does not replace a proof/invariant argument.

## Correctness and Learning Rules

- A reference output must itself match the specification.
- Distinguish algorithm defect, implementation defect, undefined behavior and missing requirement.

## Teaching Deliverable

Verification report with requirement matrix, traces/tests, correctness and complexity verdict, counterexample, correction direction and residual gaps.

## Correctness Checks

- Every defect has a reproducible input or logical argument.
- Claims of correctness and complexity match the implementation actually shown.

## Learning Failure Patterns

- **Happy-path tests only:** target each assumption and boundary.
- **Complexity copied from intended algorithm while code differs:** inspect operations.

## Handoffs

Debugging Strategy isolates implementation causes; Algorithm Analysis repairs proof/cost; Work QA handles production test systems.
