# System Decomposition

Context: [Software Architect](README.md).

## Purpose

Divide a system into responsibilities that can evolve without unnecessary coupling.

## Activate When

A system’s modules are unclear or changes spread across unrelated areas.

## Do Not Use When

[Service-boundary-design.md](service-boundary-design.md) decides deployment boundaries; decomposition does not imply microservices.

## Required Context

**Needed:** Domain workflows, change patterns, invariants, and existing dependencies.

**Can be deferred or bounded:** Deployment shape is deferred; model responsibilities before choosing services.

## Workflow

1. Inspect domain workflows and identify behavior that changes together.
2. Map invariants and data ownership before drawing module boxes.
3. Group cohesive responsibilities and define narrow contracts between them.
4. Test representative changes and failures against the proposed decomposition.

## Change-Cost Probe

Take representative changes such as a policy revision, new integration, and lifecycle transition. Trace which modules must change and which contracts should remain stable. Merge or redesign boundaries that split one invariant across multiple owners without a concrete benefit.

## Decision Rules

- If separating responsibilities splits an invariant across unreliable boundaries, keep them together or design explicit coordination.
- If a module has no independent responsibility, avoid an abstraction created only for symmetry.

## Output Contract

Responsibility map with module contracts, ownership, cohesion rationale, and coupling risks.

## Quality Gates

- Does a normal change affect a bounded set of modules?
- Is each responsibility owned once and each cross-module dependency justified?
- A normal domain change has a bounded authoritative owner and no hidden cyclic dependency.

## Failure Modes

- Technical layers mistaken for domain boundaries: examine change patterns.
- Every noun becomes a service: distinguish modules from deployments.

## Handoffs

Backend Engineer maps modules to code; Database Engineer validates ownership; Team Manager checks practical ownership.
