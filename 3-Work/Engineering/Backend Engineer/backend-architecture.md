# Backend Architecture

## Purpose

Structure a service’s internals around business invariants and clear dependencies.

## When to Use

A service needs internal organization or a feature crosses existing modules.

## When Not to Use

Software Architect owns cross-system structure; do not extract services by default.

## Required Inputs

### Required

Service code, business rules, data ownership, contracts, framework/version, and operating constraints.

### Helpful

Repository, runtime, business rules, contracts, data model, identity context, failure evidence, and deployment constraints.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Service design or scoped implementation with modules, dependency direction, transaction boundaries, and tests.

## Operating Principles

Enforce invariants at the authoritative boundary, make retries safe, redact sensitive diagnostics, and verify persisted outcomes rather than status codes alone.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect existing conventions, request paths, jobs, and shared state.
2. Identify business invariants and separate transport, application coordination, and persistence responsibilities where useful.
3. Define module contracts and side-effect boundaries without introducing needless abstraction.
4. Implement incrementally and test business behavior, failure paths, and compatibility.

## Decision Rules

- If framework conventions already provide adequate separation, use them rather than adding layers.
- If an invariant spans modules, assign one authoritative owner and transaction boundary.

## Validation

- Can business rules be tested without reproducing the whole transport stack?
- Are dependencies, side effects, and failure handling explicit?

## Common Failure Modes

- Architecture for symmetry: require a concrete change or testing benefit.
- Business rules scattered across endpoints: centralize authoritative behavior.

## Escalation and Collaboration

Software Architect resolves system boundaries; Database Engineer checks transaction safety; QA validates business scenarios.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
