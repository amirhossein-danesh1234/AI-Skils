# proof-analysis

[Mathematics Tutor](README.md) / [University domain](../../README.md)

## Mathematical Goal

Analyze or repair a proof by checking quantifiers, hypotheses and logical dependencies.

## Use This For

A proposed proof or proof idea needs validity, completeness and pedagogical explanation.

## Validity Boundary

Examples or computation may find counterexamples but cannot certify a universal claim.

## Definitions and Preconditions

Theorem statement with quantifiers, definitions, allowed results, proposed proof, context and required rigor.

## Reasoning Protocol

1. Normalize the statement into hypotheses and conclusion; identify proof type and dependencies.
2. Trace each inference, checking theorem hypotheses, quantifier scope, case coverage and whether claims are equivalent or only one-way.
3. Actively seek counterexamples at boundaries and for strengthened intermediate claims. Locate the earliest gap rather than only noting the conclusion is wrong.
4. Classify the argument as valid, repairable or false/insufficient; repair minimally and explain the key idea plus why tempting alternatives fail.

## Proof Status Labels

Mark formal proof, proof sketch, heuristic motivation and numerical evidence separately. A finite computation can prove a finite exhaustive claim, but sampled cases never prove an unrestricted universal statement.

## Validity Rules

- Circular reasoning includes importing a theorem equivalent to the target without an independent basis.
- A counterexample must satisfy all hypotheses before it refutes the conclusion.

## Mathematical Output

Proof review with normalized claim, dependency map, line-level verdict, counterexample/gap, minimal repair or revised claim and conceptual explanation.

## Independent Checks

- All cases and quantifiers are discharged.
- The repaired proof uses only allowed established results and states any new lemma.

## Logical Failure Modes

- **Diagram or plot treated as proof:** translate the needed property formally.
- **Correct conclusion hides invalid step:** verdict follows reasoning, not destination.

## Handoffs

Concept Explanation clarifies definitions; Symbolic Derivation checks algebra; Scientific Researcher handles literature attribution.
