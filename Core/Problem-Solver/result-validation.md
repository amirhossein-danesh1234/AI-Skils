# Result Validation

Context: [Problem-Solver](README.md).

## Purpose

Verify a claimed result against an independent oracle and boundaries.

## When to Use

A claimed solution, calculation, experiment or external result needs independent verification.

## Boundary

Orchestrator output-evaluation assesses the artifact, not the real-world effect.

## Inputs

Original acceptance criteria, actual candidate/result, baseline, permitted checks, boundary conditions and authoritative evidence.

## Method

1. Define an oracle appropriate to the claim: independent calculation, source record, observed behavior, domain rule or controlled test. The author’s own explanation is not sufficient verification.
2. Reproduce a material result from inputs where feasible and test boundary/negative cases. Check units, invariants, limiting cases or known relationships appropriate to the domain.
3. Separate intermediate success from user outcome: a request accepted, file produced or task marked done may not establish the intended effect. Inspect persisted or authoritative final state when required and permitted.
4. Test side effects, relevant regressions and persistence over a justified observation window. Preserve control cases and distinguish observed results from proposed tests.
5. Report verified, partially verified, contradicted or unverified with evidence and remaining gaps. A failed result can still yield a completed validation report.

## Independent Evidence

Use a check that can fail even when the original method is confidently wrong. Repeating the same calculation or asking the same model to agree may reproduce the same error. If no trustworthy oracle is accessible, state the claim as unverified and identify the smallest safe check; do not manufacture certainty through repeated review. For ambiguous external effects, reconcile before retrying.

## Output

Validation record with criteria, method, actual pass/fail/untested evidence, side effects, scope of confidence and unresolved checks.

## Quality Checks

- No unexecuted test is counted as passed and no real-world effect is inferred from a success message alone.
- The check does not perform an unauthorized consequential action merely to prove that action is possible.

## Handoffs

[Output-evaluation](../AI-Orchestrator/output-evaluation.md) checks the report/artifact; domain experts define substantive acceptance and safe verification.
