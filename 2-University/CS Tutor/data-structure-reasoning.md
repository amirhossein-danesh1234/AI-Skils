# data-structure-reasoning

[CS Tutor](README.md) / [University domain](../../README.md)

## Learning Goal

Choose and reason about data structures from operations, invariants and costs.

## Activate For

A problem requires choosing, explaining or analyzing a data representation.

## Educational Boundary

Do not select by name recognition or average complexity alone.

## Program or Problem Context

Required operations and frequencies, invariants, ordering/uniqueness needs, input scale/distribution, memory constraints, language model and candidate structures.

## Reasoning Lab

1. Translate the problem into required operations, guarantees and invariants before naming a structure.
2. Compare candidates by worst/expected/amortized cost, memory/layout, mutation/iteration semantics and how they maintain the invariant.
3. Trace representative and adversarial operation sequences, including empty, duplicate, skewed and capacity-transition cases.
4. Select conditionally, explain implementation choices at the learner’s level and derive how changing the workload could change the choice.

## Operation Profile

A structure is appropriate for an operation mix, not universally “best.” State assumptions behind expected hash cost, balanced-tree height or contiguous-memory performance, and separate abstract ADT from concrete implementation.

## Correctness and Learning Rules

- Correctness invariants outrank average speed.
- Include hidden costs such as resizing, pointer/storage overhead or maintaining auxiliary indices when material.

## Teaching Deliverable

Comparison with operation profile, candidate table, invariant reasoning, traces, complexity/memory assumptions, selection and reversal conditions.

## Correctness Checks

- The choice supports every required operation and semantic guarantee.
- Costs are derived for the actual sequence/model, not copied as isolated facts.

## Learning Failure Patterns

- **Choosing a list/tree/map by label:** start from operations.
- **Average-case guarantee stated without distribution/implementation assumption:** qualify it.

## Handoffs

Algorithm Analysis proves operations; Code Tracing illustrates mutation; professional storage design belongs to Work.
