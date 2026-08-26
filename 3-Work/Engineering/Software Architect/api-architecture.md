# API Architecture

## Purpose

Define consistent API boundaries and interaction patterns across a system.

## When to Use

Multiple services or clients need a coherent API topology and contract policy.

## When Not to Use

Backend api-design.md specifies individual endpoints; this skill governs system-wide choices.

## Required Inputs

### Required

Consumers, service ownership, interaction needs, trust boundaries, latency, compatibility, and operational constraints.

### Helpful

Current topology and code, domain rules, load evidence, quality targets, team capabilities, constraints, and migration context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

API architecture with ownership, interaction styles, identity propagation, versioning, error conventions, and governance.

## Operating Principles

Prefer a modular single deployment when adequate. Introduce distribution or abstraction only for demonstrated needs, with observable failure and recovery behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect consumer journeys and distinguish request/response, event, and bulk needs.
2. Assign authoritative service boundaries and avoid gateways that duplicate business logic.
3. Define compatibility, authentication context, rate limits, idempotency, and failure conventions.
4. Walk a cross-service request under timeout, partial failure, and version mismatch.

## Decision Rules

- If synchronous fan-out exceeds the latency or reliability budget, simplify or decouple the interaction.
- If a shared convention does not fit a legitimate use case, document a narrow exception.

## Validation

- Can consumers predict errors and compatibility behavior across APIs?
- Are data ownership and authorization context preserved through intermediaries?

## Common Failure Modes

- One protocol forced everywhere: choose by interaction needs.
- Gateway becomes hidden business service: keep ownership explicit.

## Escalation and Collaboration

Backend Engineer designs endpoints; Security checks identity and trust; DevOps evaluates routing and observability.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
