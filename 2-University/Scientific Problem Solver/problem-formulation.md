# problem-formulation

[Scientific Problem Solver](README.md) / [University domain](../../README.md)

## Scientific Aim

Turn an ambiguous scientific prompt into a well-posed target, system and success criterion.

## Entry Conditions

A scientific prompt is ambiguous, underspecified or mixes several questions.

## Modeling Boundary

Do not solve before defining the quantity, system boundary and required precision.

## Required Scientific Context

Prompt/context, decision or knowledge need, observations, system and scale, candidate outputs, constraints, available data/methods and required precision.

## Scientific Workflow

1. Separate the motivating situation from the answerable target; identify stakeholder/decision if relevant without changing the scientific question.
2. Define system boundary, state/observables, independent variables, target quantity and temporal/spatial scales.
3. List known observations, unknowns, controllable inputs, constraints and required initial/boundary conditions with evidence labels.
4. Set success/validation criteria and produce a smallest tractable question plus explicit exclusions and alternative formulations where ambiguity matters.

## Well-Posedness Test

Ask whether a solution exists under the proposed model, whether relevant outputs are unique, and whether small input changes cause tolerable output changes. An empirical question also needs observable evidence capable of discriminating alternatives.

## Model and Method Rules

- Do not hide missing information by choosing convenient values.
- Match required precision to the actual decision or academic objective.

## Scientific Deliverable

Problem statement with target, system/scales, variables, knowns/unknowns, constraints/conditions, assumptions, success criteria and unresolved questions.

## Validation Gates

- The target is measurable, computable or formally decidable under stated conditions.
- Scope excludes adjacent questions that the method cannot answer.

## Modeling Failure Modes

- **Solving the motivating story instead of defined quantity:** restate target.
- **All unknowns treated as parameters without identifiability check:** test information sufficiency.

## Handoffs

Modeling formalizes relations; Research Question handles studyable evidence; subject tutors supply domain principles.
