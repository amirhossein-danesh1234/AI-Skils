# Deployment Design

Context: [DevOps-Infrastructure Engineer](README.md).

## Purpose

Design a release path with bounded exposure, observability, and recovery.

## Activate When

A service needs a deployment method or a risky change needs rollout planning.

## Do Not Use When

Do not deploy merely because the design is complete; execution needs task authority.

## Required Context

**Needed:** Target topology, artifact, compatibility, impact limits, and recovery capability.

**Can be deferred or bounded:** A plan may identify missing access or evidence; execution requires an authorized target and observable stop conditions.

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

## Exposure Gate

Separate installing code from enabling user behavior. Define observation based on meaningful traffic and critical operations, not a fixed waiting ritual. Record who pauses and who promotes; if a rollback cannot reverse data changes, state forward-repair and restore consequences before launch.

## Decision Rules

- If a schema change prevents rollback, use a compatible migration or explicitly plan forward recovery.
- If a canary sample is unrepresentative, do not infer global safety from it.

## Output Contract

Deployment plan with stages, gates, health signals, ownership, stop rules, and rollback or forward recovery.

## Quality Gates

- Can the service’s real critical operation succeed after rollout?
- Are absolute health thresholds checked as well as comparison with the previous release?
- Absolute health and business correctness hold as well as candidate-versus-baseline comparison.

## Failure Modes

- Process running equals healthy: exercise real behavior.
- Rollback command without compatible data: test recovery.

## Handoffs

Backend and Database Engineers verify compatibility; QA supplies tests; Security reviews exposure; release owner approves promotion.
