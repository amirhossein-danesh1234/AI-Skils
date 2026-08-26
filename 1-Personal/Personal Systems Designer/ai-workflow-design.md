# ai-workflow-design

[Personal Systems Designer](README.md) / [Personal domain](../../README.md)

## Purpose

Design a bounded personal AI workflow with trusted context, human checks and stopping.

## Activate When

A personal workflow may benefit from probabilistic drafting, classification, extraction or review with explicit human authority.

## Do Not Use When

AI cannot acquire authority, truth or consent from its prompt.

## Required Context

**Needed**

Outcome, inputs/sensitivity, frequency, error consequences, human decision rights, approved tools/models and evaluation examples.

**Can be deferred or bounded**

Model/provider choice and automation may wait until a manual prototype proves value.

## Workflow

1. Define the exact assistance job and why AI is preferable to a checklist, template, search or deterministic rule.
2. Map data exposure, allowed inputs, prohibited inferences/actions and the human approval boundary. Minimize retained personal context.
3. Design input, prompt/context, structured output, validation and fallback. Build representative normal, ambiguous and harmful-error examples.
4. Run a bounded manual pilot; measure useful acceptance, correction burden, serious misses, cost and latency. Automate only after thresholds and rollback are set.

## Probabilistic Control Loop

AI output is a proposal unless the user explicitly grants bounded authority. High-consequence medical, legal, financial, employment, safety or relationship actions require qualified verification and human judgment. Never infer sensitive traits because they might improve personalization.

## Decision Rules

- Prefer no AI when deterministic logic is adequate.
- Require a safe failure state when hallucination, omission or disclosure could cause material harm.

## Output Contract

Workflow specification with job, minimal data, authority matrix, prompt/interface, validation, test set, metrics, fallback and retirement rule.

## Quality Gates

- Each consequential output has a named verifier and evidence expectation.
- The pilot tests failure handling, not only attractive examples.

## Failure Modes

- **AI inserted as novelty:** compare simpler baseline.
- **Automation sends/spends/deletes or represents user without explicit authority:** keep approval gate.

## Handoffs

Automation Design handles deterministic execution; PKM governs source records; qualified professionals validate regulated outputs.
