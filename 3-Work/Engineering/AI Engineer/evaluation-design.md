# Evaluation Design

Context: [AI Engineer](README.md).

## Purpose

Establish trustworthy evidence that an AI system satisfies its task and risk contract.

## Activate When

An AI feature, prompt, model, retrieval policy, agent, or fallback is created or changed.

## Do Not Use When

Product Analyst measures downstream user outcomes; QA validates software correctness. Neither replaces task-specific AI behavioral evaluation.

## Required Context

**Needed:** Task contract, representative cases, high-consequence failures, judging method, deployment slices, and release decision owner.

**Can be deferred or bounded:** A small reviewed seed set supports discovery only. Sample size, repetition, and release thresholds must match risk; do not invent a universal passing percentage.

## Workflow

1. Define evaluable units: response, claim, tool call, trajectory, or complete user task. Specify success, critical failure, abstention, and incomplete execution separately.
2. Build versioned development, holdout, and adversarial sets with source provenance, permitted data use, difficulty, language, user segment, and freshness. Prevent near-duplicate and future-answer leakage.
3. Choose deterministic checks for schemas/invariants, expert review for domain truth, and calibrated model graders only for suitable judgments. Test graders against human-labeled cases, disagreement, position bias, and injected scoring instructions.
4. Compare with a non-AI or prior-system baseline. Repeat stochastic cases as needed; report counts, denominators, uncertainty, severe-error rate, abstention/coverage, tail latency, and cost per successful task.
5. Inspect failures by slice and mechanism. Keep release gates separate from exploratory tuning; a strong mean cannot compensate for a critical permission or money failure.
6. Run shadow or limited exposure with safe effects, monitoring, fallback, and rollback. Convert production misses into reviewed regression cases without contaminating the untouched holdout.

## Decision Rules

- If judges disagree materially, resolve the rubric or obtain qualified review before ranking systems.
- If zero severe failures are observed in a small sample, report the limited exposure; do not claim zero risk.
- If a prompt/model/corpus/tool policy changes, rerun the affected gates and preserve the evaluated bundle identity.

## Output Contract

Evaluation packet: task/risk contract, dataset split/version, rubric, judge calibration, baseline, per-slice results with uncertainty, failure taxonomy, gate decisions, rollout and monitoring.

## Quality Gates

- A reviewer can reproduce the population, run configuration, and scoring rationale.
- No tuning or grading artifact includes hidden holdout answers.
- False acceptance, over-refusal, and human-review load are considered together; risk owner accepts residual exposure.

## Failure Modes

- Model judge agrees with its own style rather than task truth.
- Demo selection hides failures or excludes timeouts from the denominator.
- Evaluation measures a prompt while production uses a different tool/context bundle.

## Handoffs

Product Manager defines value/policy; domain experts supply truth; Security owns adversarial threat review; QA validates harness; Product Analyst measures live outcomes.

## References

[NIST Generative AI Profile, AI 600-1](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence) provides lifecycle risk context. Task-specific tests and authorized risk decisions remain necessary.
