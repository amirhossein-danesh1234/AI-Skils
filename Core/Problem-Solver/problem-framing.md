# Problem Framing

Context: [Problem-Solver](README.md).

## Purpose

Define expected versus observed behavior and the counterexample population.

## When to Use

A complaint, symptom or proposed fix does not yet define a testable problem.

## Boundary

Decision framing chooses among options; problem framing defines the gap.

## Inputs

Observed behavior, expected baseline, affected context, timeline, examples/counterexamples and consequences.

## Method

1. State observed versus expected behavior with a common unit, population and time basis. Identify who expected what and whether that expectation is a requirement, preference or untested assumption.
2. Collect a minimal reproducing or representative case and a nearby case where the problem does not occur. Record conditions and source evidence without implying prevalence from one example.
3. Separate symptom, consequence, suspected cause and proposed solution. Define scope boundaries and what would count as improvement or resolution.
4. Identify measurement gaps or conflicting definitions that must be resolved before causal work. Preserve the user’s original concern while offering a sharper testable formulation.

## Is / Is Not Boundary

Contrast where, when and for whom the gap occurs with similar unaffected cases. A useful boundary narrows possible mechanisms; an arbitrary boundary hides them. If the data cannot establish the gap, the next task is measurement verification, not implementation of the requested fix.

## Output

A testable gap statement, baseline, affected/unaffected conditions, stakes, exclusions and acceptance evidence.

## Quality Checks

- The statement can be understood without naming a preferred solution.
- Expected and observed states use compatible definitions and the claimed scope matches evidence coverage.

## Handoffs

[Decision-making](../Decision-Analyst/decision-making.md) handles a choice among acceptable alternatives; [hypothesis-generation](hypothesis-generation.md) begins explanation testing.
