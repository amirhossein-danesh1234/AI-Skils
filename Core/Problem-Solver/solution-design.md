# Solution Design

Context: [Problem-Solver](README.md).

## Purpose

Link candidate interventions to mechanisms and bounded tests.

## When to Use

A framed problem has enough mechanism evidence to compare interventions or safe experiments.

## Boundary

Domain specialists own implementation constraints.

## Inputs

Problem/acceptance contract, supported and uncertain mechanisms, constraints, feasible resources and effect authority.

## Method

1. Map each candidate to the mechanism or constraint it changes. Include no change, process/expectation adjustment, prevention, detection and bounded mitigation where relevant.
2. Compare outcome coverage, implementation/transition burden, reversibility, side effects and dependence on uncertain assumptions. Do not compare an idealized redesign with the actual current system.
3. Choose the smallest intervention that can test or solve the material gap. Define the observation window and conditions under which it is safe to expand, stop or reverse.
4. Specify preconditions, acceptance evidence, failure containment and who owns follow-through. Domain specialists validate technical, medical, legal or other professional requirements.
5. Return a recommended design or experiment with alternatives and unresolved gates; implementation remains a separate action within the real mandate.

## Mechanism-to-Outcome Bridge

A solution can remove a symptom while creating a larger problem elsewhere. Trace immediate and second-order effects on other users, resources and later periods. If causal evidence is weak, a reversible experiment may be appropriate, but state what it will teach and avoid calling its hoped-for result established.

## Output

Candidate comparison, chosen intervention/experiment, causal rationale, preconditions, acceptance and stop/recovery conditions.

## Quality Checks

- The proposed intervention tests or changes a named mechanism and preserves hard constraints.
- A fallback is actually feasible and its activation does not require authority that has not been granted.

## Handoffs

[Planner](../Planner/README.md) sequences an accepted intervention; [result-validation](result-validation.md) verifies actual outcomes.
