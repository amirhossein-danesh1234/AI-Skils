# Backend Engineer — Code Review

Context: [Backend Engineer](README.md).

## Purpose

Review backend changes for invariant, contract, security, and failure correctness.

## Activate When

A service diff needs review before acceptance or release.

## Do Not Use When

Do not turn review into an unrelated refactor or report speculative style issues as defects.

## Required Context

**Needed:** Diff, business rules, consumers, database behavior, and deployment context.

**Can be deferred or bounded:** Tests not executed remain unverified; static review can still identify a concrete reachable defect.

## Workflow

1. Trace changed operations through validation, authorization, state changes, and side effects.
2. Inspect concurrency, repeated requests, error handling, migration compatibility, and sensitive logging.
3. Check tests against business invariants and missing negative cases.
4. Prioritize confirmed risks and distinguish questions, blockers, and optional improvements.

## Failure-Oriented Review

Trace one normal request and the same request denied, concurrent, repeated, and interrupted around persistence or an external effect. Check old/new application versions against migration order. Prioritize data integrity, access, and irreversible effects above style preferences or speculative abstraction.

## Decision Rules

- If the change affects shared contracts, inspect representative consumers and version compatibility.
- If a finding depends on an assumption, state it and seek confirming evidence.

## Output Contract

Actionable findings with concrete failure scenario, impact, evidence, and suggested scope of correction.

## Quality Gates

- Can each issue be demonstrated from a reachable path?
- Are tests claimed only when actually executed?
- A finding states the triggering conditions, actual risk, and smallest correction supported by evidence.

## Failure Modes

- Happy-path review misses retries: trace ambiguous failures.
- Refactor preference masks correctness: focus on behavior and risk.

## Handoffs

Security Engineer reviews trust-sensitive changes; Database Engineer reviews integrity; QA validates regression coverage.
