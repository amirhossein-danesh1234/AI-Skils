# algorithm-analysis

[CS Tutor](README.md) / [University domain](../../README.md)

## Learning Goal

Explain algorithm correctness and derive time and space complexity.

## Activate For

A learner must understand why an algorithm works and what resources it consumes.

## Educational Boundary

Academic reasoning only; production performance engineering belongs to Work.

## Program or Problem Context

Algorithm/pseudocode, input model and size variables, pre/postconditions, computational model, learner prerequisites and relevant constraints.

## Reasoning Lab

1. Specify the problem, valid inputs, output condition and size measure; identify the algorithm’s state and key invariant.
2. Prove partial correctness around initialization, maintenance and termination, or state the appropriate induction/exchange/contradiction argument.
3. Count dominant operations by cases, loops/recurrences or amortized reasoning; derive time and auxiliary-space bounds with assumptions.
4. Test edge and adversarial examples, compare a plausible alternative and explain when asymptotic versus practical costs matter.

## Correctness–Cost Pair

A fast procedure that violates the specification is not an algorithmic solution. Keep worst, average, expected and amortized bounds distinct; identify probability assumptions and whether input/output storage is counted.

## Correctness and Learning Rules

- Big-O is an upper-bound relation, not automatically a tight worst-case bound.
- A recurrence solution must state base cases and justify the recurrence.

## Teaching Deliverable

Teaching analysis with specification, invariant/correctness argument, termination, complexity derivation, edge traces, comparison and learner check.

## Correctness Checks

- The complexity uses the declared size variable and model.
- Correctness covers all valid inputs or clearly labels an unproved conjecture.

## Learning Failure Patterns

- **Counting nested loops by visual nesting alone:** inspect dependent bounds.
- **One successful trace presented as proof:** connect trace to invariant.

## Handoffs

Code Tracing illustrates cases; Data Structure Reasoning supplies operation costs; Mathematics Tutor supports proof/recurrences.
