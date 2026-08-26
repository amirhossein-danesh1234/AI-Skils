# Backend Architecture

Context: [Backend Engineer](README.md).

## Purpose

Structure a service’s internals around business invariants and clear dependencies.

## Activate When

A service needs internal organization or a feature crosses existing modules.

## Do Not Use When

Software Architect owns cross-system structure; do not extract services by default.

## Required Context

**Needed:** Current service code, domain invariants, persistence, and framework constraints.

**Can be deferred or bounded:** Cross-service extraction is a separate architecture decision; local modularity can proceed without it.

## Workflow

1. Inspect existing conventions, request paths, jobs, and shared state.
2. Identify business invariants and separate transport, application coordination, and persistence responsibilities where useful.
3. Define module contracts and side-effect boundaries without introducing needless abstraction.
4. Implement incrementally and test business behavior, failure paths, and compatibility.

## Invariant Owner

Identify where each rule is enforced across endpoints, jobs, admin operations, and integrations. Keep transport parsing separate from reusable domain behavior when it prevents divergent enforcement, but do not add layers without a testability or change-isolation benefit.

## Decision Rules

- If framework conventions already provide adequate separation, use them rather than adding layers.
- If an invariant spans modules, assign one authoritative owner and transaction boundary.

## Output Contract

Service design or scoped implementation with modules, dependency direction, transaction boundaries, and tests.

## Quality Gates

- Can business rules be tested without reproducing the whole transport stack?
- Are dependencies, side effects, and failure handling explicit?
- Equivalent operations through different entry points enforce the same business invariant.

## Failure Modes

- Architecture for symmetry: require a concrete change or testing benefit.
- Business rules scattered across endpoints: centralize authoritative behavior.

## Handoffs

Software Architect resolves system boundaries; Database Engineer checks transaction safety; QA validates business scenarios.
