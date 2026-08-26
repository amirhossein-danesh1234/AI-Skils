# API Architecture

Context: [Software Architect](README.md).

## Purpose

Define consistent API boundaries and interaction patterns across a system.

## Activate When

Multiple services or clients need a coherent API topology and contract policy.

## Do Not Use When

Backend [api-design.md](../Backend%20Engineer/api-design.md) specifies individual endpoints; this skill governs system-wide choices.

## Required Context

**Needed:** Consumer interactions, service/data ownership, and trust boundaries.

**Can be deferred or bounded:** Detailed endpoint payloads belong to Backend; numerical budgets require measured or owner-approved targets.

## Workflow

1. Inspect consumer journeys and distinguish request/response, event, and bulk needs.
2. Assign authoritative service boundaries and avoid gateways that duplicate business logic.
3. Define compatibility, authentication context, rate limits, idempotency, and failure conventions.
4. Walk a cross-service request under timeout, partial failure, and version mismatch.

## Cross-Service Contract

Trace an authenticated request through gateway, service, queue, and callback where relevant. Mark which identity is propagated, which permission is rechecked, and where a deadline is consumed. A gateway may route and apply common policy but should not become an unowned second implementation of business rules.

## Decision Rules

- If synchronous fan-out exceeds the latency or reliability budget, simplify or decouple the interaction.
- If a shared convention does not fit a legitimate use case, document a narrow exception.

## Output Contract

API architecture with ownership, interaction styles, identity propagation, versioning, error conventions, and governance.

## Quality Gates

- Can consumers predict errors and compatibility behavior across APIs?
- Are data ownership and authorization context preserved through intermediaries?
- One cross-service failure can be explained without assuming every dependency succeeds.

## Failure Modes

- One protocol forced everywhere: choose by interaction needs.
- Gateway becomes hidden business service: keep ownership explicit.

## Handoffs

Backend Engineer designs endpoints; Security checks identity and trust; DevOps evaluates routing and observability.
