# Hallucination Control

Context: [AI Engineer](README.md).

## Purpose

Reduce unsupported factual claims and unsafe confidence without suppressing useful supported answers.

## Activate When

An AI task relies on factual or source-grounded accuracy.

## Do Not Use When

This is not general content moderation; source presence and model confidence do not prove factual support.

## Required Context

**Needed:** Claim types, available evidence, acceptable abstention, error harm, and examples of supported/unsupported answers.

**Can be deferred or bounded:** Calibrated thresholds require held-out evidence; start with explicit evidence requirements rather than trusting self-reported certainty.

## Workflow

1. Classify claims by required evidence: supplied fact, corpus-supported statement, calculation, current external fact, or explicitly requested inference.
2. Require evidence retrieval or deterministic calculation for claims that need it. Bind citations to actual passages and preserve qualifiers, dates, units, and contradictory evidence.
3. Check output claim-by-claim where risk warrants: support, entailment, numerical consistency, source authority, and whether the response overstates the source.
4. Define abstention, targeted clarification, partial answer, or human review for unsupported claims. Avoid forcing a complete answer when coverage is incomplete.
5. Evaluate unsupported-claim rate alongside useful coverage, false abstention, cost, and harmful overconfidence across stale, contradictory, and unanswerable cases.

## Decision Rules

- If evidence supports only a weaker claim, narrow the wording instead of attaching a citation to the stronger claim.
- If verification uses another model, measure its misses and correlated errors; agreement is not independent truth.

## Output Contract

Claim/evidence policy, verification method, abstention behavior, evaluation results, remaining error classes, and review routing.

## Quality Gates

- Known unsupported and contradictory cases are not answered with fabricated citations.
- Supported answers remain usable rather than being universally refused.

## Failure Modes

- Citation exists but does not entail the claim.
- Numeric confidence emitted by the model is treated as calibrated probability.

## Handoffs

rag-design provides evidence path; structured-output represents unknowns; domain expert validates consequential truth.
