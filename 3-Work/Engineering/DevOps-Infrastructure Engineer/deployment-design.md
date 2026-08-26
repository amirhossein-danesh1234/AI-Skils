# Deployment Design

## Purpose

Design a release path with bounded exposure, observability, and recovery.

## When to Use

A service needs a deployment method or a risky change needs rollout planning.

## When Not to Use

Do not deploy merely because the design is complete; execution needs task authority.

## Required Inputs

### Required

Topology, artifact, compatibility, traffic, state changes, objectives, and operational access.

### Helpful

Actual infrastructure and listeners, release process, identities, dependencies, service objectives, secrets handling, and current incident state.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Deployment plan with stages, gates, health signals, ownership, stop rules, and rollback or forward recovery.

## Operating Principles

Inspect before mutation; use immutable or traceable releases, least privilege, explicit stop conditions, and real service checks.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect existing services, listeners, proxying, state, and current release process.
2. Choose a rollout pattern matching traffic, reversibility, and application/data compatibility.
3. Define preflight checks, smoke tests, observation duration, and user-impact signals.
4. Rehearse recovery and specify who stops or promotes each stage.

## Rollout Gates

1. **Preflight:** verify target environment, artifact identity, configuration, secrets references, compatibility, backup or recovery readiness, service ownership, and authorized change window. Preserve unrelated listeners and access paths.
2. **Introduce:** deploy with bounded exposure appropriate to the system. A canary requires a meaningful sample and a control or baseline; low traffic may require a longer observation period or a different verification approach.
3. **Observe:** compare errors, latency, saturation, and business-operation correctness. Check absolute acceptable behavior as well as candidate-versus-baseline differences, since both can fail together. Define who can pause promotion.
4. **Promote or recover:** promote only after the stated gates; otherwise stop, isolate, roll back compatible code, or execute the planned forward-repair path. Capture evidence before it disappears, without delaying urgent containment.
5. **Close:** verify the real user or service operation, persistence after restart where relevant, monitoring, and operator handoff. Record the deployed artifact and any cleanup still pending.

Google’s [canary release guidance](https://sre.google/workbook/canarying-releases/) informs bounded exposure and evaluation. Adapt it to the actual traffic and architecture; a startup does not need a complex rollout platform merely to satisfy this protocol.

## Decision Rules

- If a schema change prevents rollback, use a compatible migration or explicitly plan forward recovery.
- If a canary sample is unrepresentative, do not infer global safety from it.

## Validation

- Can the service’s real critical operation succeed after rollout?
- Are absolute health thresholds checked as well as comparison with the previous release?

## Common Failure Modes

- Process running equals healthy: exercise real behavior.
- Rollback command without compatible data: test recovery.

## Escalation and Collaboration

Backend and Database Engineers verify compatibility; QA supplies tests; Security reviews exposure; release owner approves promotion.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
