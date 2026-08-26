# Structured Output

Context: [AI Engineer](README.md).

## Purpose

Make model-produced data safe for a deterministic consumer to parse and validate.

## Activate When

An AI output feeds an API, database, workflow, or machine-readable report.

## Do Not Use When

Valid JSON is not factual correctness or authorization; Backend Engineer owns business invariants.

## Required Context

**Needed:** Consumer schema, field semantics, allowed values, missing-value policy, and error consequences.

**Can be deferred or bounded:** Provider constraint syntax can be selected later; inspect supported schema features for the actual model/version before implementation.

## Workflow

1. Define field types, units, null versus absent meaning, enums, required fields, cross-field rules, and provenance. Represent unknowns explicitly rather than coercing them to plausible defaults.
2. Use supported constrained output or tool schemas where useful. Treat model output as untrusted regardless of decoding guarantees.
3. Validate parse/schema first, then semantic ranges, references, relationships, policy, and evidence. Do not execute a tool or persist consequential data before all applicable checks.
4. Design bounded repair using the specific validation error, with the original task preserved. Classify refusal, truncation, timeout, and invalid content separately; never repair missing evidence by guessing.
5. Test adversarial strings, enum drift, large numbers, mixed units, missing fields, contradictory fields, and downstream escaping. Version schema and consumer compatibility.

## Decision Rules

- If validation fails after the repair budget, return a typed failure or human handoff rather than silently dropping fields.
- If a syntactically valid field would cause a consequential action, recheck its business validity at the trusted service boundary.

## Output Contract

Schema and semantic validation contract, examples of valid/invalid/unknown cases, repair budget, failure states, and consumer compatibility tests.

## Quality Gates

- The consumer rejects schema-valid but semantically invalid examples.
- No partial or refused generation is counted as a valid task completion.

## Failure Modes

- JSON parsing used as truth validation.
- Repair loop repeatedly spends tokens without a stopping rule.

## Handoffs

Backend implements authoritative validation; QA tests consumer behavior; hallucination-control evaluates evidence support.
