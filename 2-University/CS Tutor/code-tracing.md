# code-tracing

[CS Tutor](README.md) / [University domain](../../README.md)

## Learning Goal

Trace execution state precisely to explain program behavior.

## Activate For

A program fragment’s exact execution or state transition is unclear.

## Educational Boundary

Use a defined language/version and input; tracing one case does not prove all cases.

## Program or Problem Context

Complete code/pseudocode, language and version semantics, input, initial state/environment, relevant evaluation-order rules and learner prediction.

## Reasoning Lab

1. Freeze the exact program and semantics; identify entry point, inputs, mutable state, call stack/heap objects and possible nondeterminism.
2. Step through control flow in evaluation order using a trace table. Record only state that changes or determines the next branch.
3. Track aliases, scope/lifetime, recursion frames, side effects and exceptions explicitly; branch when behavior depends on unspecified or concurrent ordering.
4. Compare final state/output with the learner’s prediction, locate the first divergence and generalize the governing concept with another input.

## Trace Table Contract

Use columns appropriate to the language: step/line, condition, variable/object state, stack or queue, output and next control location. A trace explains one execution; general correctness needs an invariant or exhaustive argument.

## Correctness and Learning Rules

- Do not assume evaluation or iteration order not guaranteed by the language.
- Represent aliases as shared identity rather than copied values.

## Teaching Deliverable

Execution trace with semantics, initial state, ordered transitions, output/exception, first misconception and transfer trace prompt.

## Correctness Checks

- Every state change follows an executed statement.
- The conclusion distinguishes deterministic behavior from implementation-dependent or nondeterministic outcomes.

## Learning Failure Patterns

- **Skipping “obvious” iterations hides off-by-one errors:** show boundary transitions.
- **Mutability/aliasing treated as value copy:** track identity.

## Handoffs

Debugging Strategy uses traces to discriminate hypotheses; Algorithm Analysis generalizes behavior; Work engineering handles production runtime issues.
