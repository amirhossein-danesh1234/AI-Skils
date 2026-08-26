# API Security

Context: [Security Engineer](README.md).

## Purpose

Assess an API’s exposure to unauthorized access, input abuse, and resource exhaustion.

## Activate When

An API is added, exposed externally, or materially changed.

## Do Not Use When

Do not apply generic rate limits without understanding business abuse and legitimate consumers.

## Required Context

**Needed:** API surface, actor types, sensitive flows, and authorized test scope.

**Can be deferred or bounded:** Traffic estimates can be provisional; business-abuse limits need policy owners before consequential rollout.

## Workflow

1. Inventory operations and distinguish public, authenticated, privileged, and machine consumers.
2. Inspect object/function authorization, input binding, output filtering, and sensitive business flows.
3. Evaluate resource limits, pagination, uploads, SSRF exposure, webhooks, and dependency calls where relevant.
4. Test bounded abuse cases and define telemetry and response for rejected or suspicious activity.

## Abuse Path

Trace a low-cost request into expensive queries, fan-out, uploads, exports, or third-party charges. Test object/function authorization, over-posting, output filtering, and rate/concurrency limits at the actual effect boundary. Validate that rejected requests cannot reveal sensitive object existence unnecessarily.

## Decision Rules

- If arbitrary client fields bind to privileged model fields, enforce an explicit allowlist.
- If an operation can trigger expensive downstream work, control cost and concurrency as well as request count.

## Output Contract

API risk assessment with abuse paths, controls, tests, and operational detection.

## Quality Gates

- Do controls address the actual reachable abuse paths?
- Are errors and responses free of unnecessary sensitive information?
- A valid login cannot bypass resource scope or trigger unbounded downstream work.

## Failure Modes

- Authentication mistaken for complete API security: inspect authorization and business abuse.
- Unlimited payload or fan-out: bound resources.

## Handoffs

Backend Engineer implements contracts; DevOps manages edge controls; QA validates abuse cases.
