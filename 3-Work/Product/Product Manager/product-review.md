# Product Review

Context: [Product Manager](README.md).

## Purpose

Evaluate whether a product increment achieved its intended user and business outcome.

## Activate When

A prototype, release, or live feature needs a continue, revise, expand, or stop decision.

## Do Not Use When

QA [release-quality-review.md](../../Engineering/QA-Test%20Engineer/release-quality-review.md) assesses test confidence; this skill evaluates product value and learning.

## Required Context

**Needed:** Original outcome, released/prototype scope, actual usage evidence, and observation window.

**Can be deferred or bounded:** Immature outcomes justify a scheduled later review, not a success claim; initial qualitative evidence can narrow hypotheses.

## Workflow

1. Inspect the original decision and expected outcomes before looking at presentation polish.
2. Compare actual adoption and task success with the relevant baseline and segment.
3. Reconcile qualitative feedback, quantitative signals, defects, and support burden.
4. Decide whether to continue, revise, narrow, or stop and update assumptions.

## Underperformance Triage

First check exposure and instrumentation, then comprehension/activation, successful value delivery, recurring value, and economics. Choose the next action by the binding failure: measurement repair, UX change, reliability fix, narrower audience, or stop. Keep Analyst’s evidence conclusion distinct from the product action decision.

## Decision Rules

- If acceptance passes but user value is absent, do not call the product successful.
- If measurement is invalid or immature, recommend an evidence repair or later review.

## Output Contract

Outcome review with evidence, deviations, unintended effects, decision, and next learning or correction.

## Quality Gates

- Are outcomes distinguished from output and attribution limits stated?
- Does the next action address the largest remaining uncertainty or failure?
- The review distinguishes not exposed, not adopted, not useful, and not measurable.

## Failure Modes

- Demo enthusiasm substituted for results: inspect real use.
- Confirmation bias: include disconfirming feedback and costs.

## Handoffs

Product Analyst validates evidence; UX investigates friction; engineering explains reliability; Product Strategist assesses direction.
