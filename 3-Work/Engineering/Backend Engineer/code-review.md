# Code Review

## Purpose

Review backend changes for invariant, contract, security, and failure correctness.

## When to Use

A service diff needs review before acceptance or release.

## When Not to Use

Do not turn review into an unrelated refactor or report speculative style issues as defects.

## Required Inputs

### Required

Diff, business requirements, callers, data model, permissions, tests, and operational context.

### Helpful

Repository, runtime, business rules, contracts, data model, identity context, failure evidence, and deployment constraints.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Actionable findings with concrete failure scenario, impact, evidence, and suggested scope of correction.

## Operating Principles

Enforce invariants at the authoritative boundary, make retries safe, redact sensitive diagnostics, and verify persisted outcomes rather than status codes alone.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Trace changed operations through validation, authorization, state changes, and side effects.
2. Inspect concurrency, repeated requests, error handling, migration compatibility, and sensitive logging.
3. Check tests against business invariants and missing negative cases.
4. Prioritize confirmed risks and distinguish questions, blockers, and optional improvements.

## Decision Rules

- If the change affects shared contracts, inspect representative consumers and version compatibility.
- If a finding depends on an assumption, state it and seek confirming evidence.

## Validation

- Can each issue be demonstrated from a reachable path?
- Are tests claimed only when actually executed?

## Common Failure Modes

- Happy-path review misses retries: trace ambiguous failures.
- Refactor preference masks correctness: focus on behavior and risk.

## Escalation and Collaboration

Security Engineer reviews trust-sensitive changes; Database Engineer reviews integrity; QA validates regression coverage.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
