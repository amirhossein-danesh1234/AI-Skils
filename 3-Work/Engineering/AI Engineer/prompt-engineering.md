# Prompt Engineering

Context: [AI Engineer](README.md).

## Purpose

Design and test instructions that reliably elicit the required task behavior.

## Activate When

A model misunderstands a stable task or the prompt contract needs a controlled revision.

## Do Not Use When

Context-engineering selects information; prompt wording cannot enforce server permissions or repair missing source facts.

## Required Context

**Needed:** Task examples, expected behavior and exclusions, current prompt/configuration, and failure cases.

**Can be deferred or bounded:** A small expert-labeled seed set permits initial iteration; keep independent holdout cases before claiming improvement.

## Workflow

1. Classify failures as instruction ambiguity, missing evidence, model limit, schema error, or tool failure; change the prompt only when instruction design can affect the cause.
2. Write concise task instructions, output constraints, ambiguity/abstention behavior, and a few discriminating examples. Keep task data visibly separate from trusted instructions.
3. Test difficult counterexamples and conflicting input, varying one material instruction at a time. Do not optimize only the examples used to write the prompt.
4. Evaluate success, over-refusal, invented facts, format errors, and length/latency trade-offs across repeated runs. Remove redundant rules whose ablation shows no value.
5. Version the prompt with model, parameters, examples, eval results, and rollback candidate. Preserve the user task rather than steering all requests into one format.

## Decision Rules

- If improvement on tuning cases harms holdout or a critical slice, reject or narrow the revision.
- If the prompt needs a long list of exceptions, revisit task decomposition or deterministic validation.

## Output Contract

Versioned prompt change with failure hypothesis, changed behavior, examples, comparative evidence, limits, and rollback.

## Quality Gates

- Unseen task variants meet the output contract without relying on copied answers.
- Untrusted input does not become permission to broaden the task.

## Failure Modes

- More instructions assumed better: test context cost and contradictions.
- Prompt optimization leaks holdout answers into examples.

## Handoffs

structured-output handles schema constraints; context-engineering handles missing evidence; Security reviews injection risk when external input is involved.
