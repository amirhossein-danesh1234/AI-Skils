# API Security

## Purpose

Assess an API’s exposure to unauthorized access, input abuse, and resource exhaustion.

## When to Use

An API is added, exposed externally, or materially changed.

## When Not to Use

Do not apply generic rate limits without understanding business abuse and legitimate consumers.

## Required Inputs

### Required

Contracts, trust boundaries, auth, data classification, traffic limits, and authorized test scope.

### Helpful

Architecture and code, data classification, actors, trust boundaries, exposure, existing controls, and authorized test scope.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

API risk assessment with abuse paths, controls, tests, and operational detection.

## Operating Principles

Separate confirmed vulnerability from suspected weakness; prioritize reachable impact and never include usable secrets or unnecessary exploit detail in public artifacts.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inventory operations and distinguish public, authenticated, privileged, and machine consumers.
2. Inspect object/function authorization, input binding, output filtering, and sensitive business flows.
3. Evaluate resource limits, pagination, uploads, SSRF exposure, webhooks, and dependency calls where relevant.
4. Test bounded abuse cases and define telemetry and response for rejected or suspicious activity.

## Decision Rules

- If arbitrary client fields bind to privileged model fields, enforce an explicit allowlist.
- If an operation can trigger expensive downstream work, control cost and concurrency as well as request count.

## Validation

- Do controls address the actual reachable abuse paths?
- Are errors and responses free of unnecessary sensitive information?

## Common Failure Modes

- Authentication mistaken for complete API security: inspect authorization and business abuse.
- Unlimited payload or fan-out: bound resources.

## Escalation and Collaboration

Backend Engineer implements contracts; DevOps manages edge controls; QA validates abuse cases.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
