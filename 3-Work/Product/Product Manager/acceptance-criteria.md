# Acceptance Criteria

Context: [Product Manager](README.md).

## Purpose

Define observable conditions that prove an agreed requirement is satisfied.

## Activate When

A story or feature lacks a clear pass/fail oracle.

## Do Not Use When

Do not invent requirements or prescribe tests that verify implementation details instead of behavior.

## Required Context

**Needed:** Agreed behavior, actor, preconditions, and expected observable effects.

**Can be deferred or bounded:** Implementation details and test tooling can be deferred; unresolved policy means the affected criterion is not ready.

## Workflow

1. Inspect the requirement and distinguish acceptance from optional quality improvements.
2. State initial conditions, action or event, and observable result for each material behavior.
3. Add boundary values, invalid inputs, repeated actions, and unauthorized actors where relevant.
4. Review each criterion for determinism and trace it to a requirement.

## Acceptance Oracle

For each rule, include one passing case and one near-miss that must fail. For money or permissions, assert persisted effects and absence of forbidden changes, not only the visible message. Keep a trace from criterion to requirement so a new criterion cannot silently add scope.

## Decision Rules

- If expected behavior is unknown, ask the policy owner; do not let a test encode an invented rule.
- If the result is subjective, define an agreed review method or measurable proxy.

## Output Contract

Acceptance criteria with normal, boundary, error, permission, and recovery examples plus unresolved questions.

## Quality Gates

- Would independent reviewers reach the same pass/fail judgment?
- Are exceptions and negative permissions covered without expanding scope?
- Two independent reviewers can judge the same case without inventing policy.

## Failure Modes

- Criteria repeat the feature title: define observable outcomes.
- UI-only checks miss persisted behavior: include authoritative effects.

## Handoffs

QA converts criteria into tests; Backend and UX specialists resolve observable system and interaction behavior.
