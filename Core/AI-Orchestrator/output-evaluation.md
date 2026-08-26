# Output Evaluation

Context: [AI-Orchestrator](README.md).

## Purpose

Evaluate an artifact against task acceptance with bounded critique loops.

## When to Use

A generated answer, plan, artifact or agent contribution needs a readiness judgment against the user task.

## Boundary

Artifact quality is not proof that an external result occurred.

## Inputs

Actual candidate/version, task requirements, audience, consequential claims, acceptance evidence and known limits.

## Method

1. Translate the request into a small set of observable acceptance checks. Separate hard failures from quality preferences; weight effort by consequences rather than treating every typo like a policy breach.
2. Inspect the actual artifact, not its author’s summary. Trace material claims to consulted evidence, check requested scope and compare figures, dates and commitments across sections.
3. Test the weakest relevant boundary: unsupported certainty, omitted exception, contradictory requirement, unusable output, broken reference or claimed action without execution evidence. Use a realistic counterexample rather than a generic praise/critique prompt.
4. Classify each issue as demonstrated defect, evidence gap or preference, with the affected requirement and smallest correction. Preserve successful parts. Verify corrected behavior against the failed case and a legitimate control.
5. Return accepted, conditionally usable with explicit limits, or not accepted with the specific blocking check. The actual release/publication owner decides consequential exposure.

## Critique Loop Stop

One self-consistent explanation is not an independent oracle. Use raw artifacts, calculations, authoritative records or independent review where risk warrants. Same-model grading needs calibration and cannot be treated as objective truth. After a correction, rerun affected checks; reopen unrelated areas only if the change can affect them. Stop at supported acceptance, a non-actionable preference, budget exhaustion or a genuine evidence/authority blocker—not after a fixed number of compliments.

## Output

Readiness verdict, failed/passed/untested checks, concrete evidence, corrections verified and residual limitations.

## Quality Checks

- No “passed” label is inferred from unexecuted tests or from the absence of visible errors.
- Artifact completeness is kept distinct from successful real-world execution; uncertainty survives the final wording.

## Handoffs

Use [result-validation](../Problem-Solver/result-validation.md) when the underlying effect or solution needs verification, and domain experts for substantive correctness.
