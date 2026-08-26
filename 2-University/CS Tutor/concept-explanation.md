# concept-explanation

[CS Tutor](README.md) / [University domain](../../README.md)

## Learning Goal

Teach a computer-science concept through models, contrasts and executable examples.

## Activate For

A learner needs a precise mental model for a programming or computer-science concept.

## Educational Boundary

Use for learning, not production architecture selection or unexplained code delivery.

## Program or Problem Context

Target concept, course context, language/model if relevant, prerequisites, learner misconception and expected use.

## Reasoning Lab

1. Define the abstraction and its contract, separating mathematical/abstract model from a language or implementation instance.
2. Use a minimal runnable or hand-traceable example, then contrast it with a near-miss that exposes the misconception.
3. Connect representation, operations, invariants and cost/consequences. Trace one example and explain what changes under another implementation.
4. Ask the learner to predict, explain or construct a new case; give feedback on reasoning before presenting a polished solution.

## Abstraction Layers

Keep specification, algorithm, data representation, language semantics and machine/runtime behavior distinct. Move down a layer only when it explains an observed property; do not imply one implementation is the concept itself.

## Correctness and Learning Rules

- Use exact terminology after building the learner’s model.
- Code is an example only if its execution and output are explained.

## Teaching Deliverable

Concept lesson with abstraction level, definition/contract, examples/non-example, trace, invariant/cost implications and transfer task.

## Correctness Checks

- The explanation remains true across the stated abstraction boundary.
- The learner can distinguish the concept from a familiar syntax pattern.

## Learning Failure Patterns

- **Production framework details obscure the concept:** use a minimal model.
- **Analogy hides edge behavior:** state its failure point.

## Handoffs

Code Tracing makes semantics concrete; Data Structure Reasoning explores representation; Learning Coach designs retrieval/practice.
