# System Decomposition

## Purpose

Divide a system into responsibilities that can evolve without unnecessary coupling.

## When to Use

A system’s modules are unclear or changes spread across unrelated areas.

## When Not to Use

Service-boundary-design.md decides deployment boundaries; decomposition does not imply microservices.

## Required Inputs

### Required

Business capabilities, change patterns, invariants, code dependencies, and team ownership.

### Helpful

Current topology and code, domain rules, load evidence, quality targets, team capabilities, constraints, and migration context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Responsibility map with module contracts, ownership, cohesion rationale, and coupling risks.

## Operating Principles

Prefer a modular single deployment when adequate. Introduce distribution or abstraction only for demonstrated needs, with observable failure and recovery behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect domain workflows and identify behavior that changes together.
2. Map invariants and data ownership before drawing module boxes.
3. Group cohesive responsibilities and define narrow contracts between them.
4. Test representative changes and failures against the proposed decomposition.

## Decision Rules

- If separating responsibilities splits an invariant across unreliable boundaries, keep them together or design explicit coordination.
- If a module has no independent responsibility, avoid an abstraction created only for symmetry.

## Validation

- Does a normal change affect a bounded set of modules?
- Is each responsibility owned once and each cross-module dependency justified?

## Common Failure Modes

- Technical layers mistaken for domain boundaries: examine change patterns.
- Every noun becomes a service: distinguish modules from deployments.

## Escalation and Collaboration

Backend Engineer maps modules to code; Database Engineer validates ownership; Team Manager checks practical ownership.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
