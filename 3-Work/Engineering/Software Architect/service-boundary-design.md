# Service Boundary Design

## Purpose

Decide whether and where independently operated services are justified.

## When to Use

A module may need separate deployment, scaling, ownership, or failure isolation.

## When Not to Use

Do not extract a service solely because a codebase is large.

## Required Inputs

### Required

Domain boundaries, invariants, workload, change cadence, team operations, and current coupling.

### Helpful

Current topology and code, domain rules, load evidence, quality targets, team capabilities, constraints, and migration context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Boundary decision with ownership, contracts, consistency model, failure isolation, deployment needs, and extraction path.

## Operating Principles

Prefer a modular single deployment when adequate. Introduce distribution or abstraction only for demonstrated needs, with observable failure and recovery behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect evidence for independent scale, release cadence, or isolation requirements.
2. Map synchronous dependencies and transactions crossing the proposed boundary.
3. Compare in-process modularity with a separate service including network, data, observability, and on-call cost.
4. Define degraded behavior, compatibility, ownership, and migration sequence if extraction is warranted.

## Decision Rules

- If the service cannot fail independently without cascading failure, revisit the boundary.
- If cross-boundary transactions dominate, prefer colocation unless coordination cost is justified.

## Validation

- Are ownership, latency budgets, retries, and versioning explicit?
- Can the team deploy, observe, and recover the service independently?

## Common Failure Modes

- Distributed monolith: test runtime coupling.
- Shared database silently defeats ownership: define allowed access contracts.

## Escalation and Collaboration

Backend and Database Engineers assess consistency; DevOps validates independent operation; Security reviews trust changes.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
