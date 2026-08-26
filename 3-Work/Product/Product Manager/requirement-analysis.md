# Requirement Analysis

Context: [Product Manager](README.md).

## Purpose

Resolve ambiguity, conflict, and incompleteness in proposed requirements.

## Activate When

Requirements arrive from multiple sources or contain unclear rules and dependencies.

## Do Not Use When

This is not backlog ordering or permission to change stakeholder intent silently.

## Required Context

**Needed:** Source wording, stakeholders, existing behavior, and constraints.

**Can be deferred or bounded:** Missing decisions can remain explicit gaps; preserve the source language when normalization risks changing intent.

## Workflow

1. Inspect source wording and distinguish needs, constraints, solutions, and preferences.
2. Rewrite ambiguous statements into observable behavior without inventing policy.
3. Check actor, preconditions, data, state transitions, exceptions, and nonfunctional constraints.
4. Resolve contradictions with the responsible owner and document the effect on scope and acceptance.

## Conflict Resolution Record

Classify each statement as need, constraint, preference, proposed solution, or approved rule. For contradictions, record both sources, affected scenario, possible resolutions, and the authorized decision. Replace adjectives with contextual acceptance methods, without inventing numeric targets.

## Decision Rules

- If two requirements cannot both hold, expose the conflict rather than choosing the easier one.
- If wording is merely a preference, label it and assess alternatives.

## Output Contract

Normalized requirement set with conflicts, assumptions, traceability, gaps, and resolution decisions.

## Quality Gates

- Are requirements individually testable and collectively consistent?
- Are source intent and unresolved decisions traceable?
- Every normalized rule has provenance and unresolved conflicts remain visible to implementers.

## Failure Modes

- Silent assumption becomes requirement: label provenance.
- Unbounded adjectives such as fast: request a contextual measurable target.

## Handoffs

Product owner resolves policy; Architect evaluates quality constraints; QA challenges testability.
