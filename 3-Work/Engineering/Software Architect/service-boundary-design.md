# Service Boundary Design

Context: [Software Architect](README.md).

## Purpose

Decide whether and where independently operated services are justified.

## Activate When

A module may need separate deployment, scaling, ownership, or failure isolation.

## Do Not Use When

Do not extract a service solely because a codebase is large.

## Required Context

**Needed:** Proposed responsibility, crossing invariants, change/scale needs, and operating capacity.

**Can be deferred or bounded:** A code module may be the first step; independent deployment is not required to establish a boundary.

## Workflow

1. Inspect evidence for independent scale, release cadence, or isolation requirements.
2. Map synchronous dependencies and transactions crossing the proposed boundary.
3. Compare in-process modularity with a separate service including network, data, observability, and on-call cost.
4. Define degraded behavior, compatibility, ownership, and migration sequence if extraction is warranted.

## Extraction Test

Compare keeping a module in-process against a separate service with network failure, version skew, data ownership, and on-call cost. Walk a failed downstream call and a mixed-version release. If independent deployability requires coordinated releases every time, name the distributed-monolith consequence.

## Decision Rules

- If the service cannot fail independently without cascading failure, revisit the boundary.
- If cross-boundary transactions dominate, prefer colocation unless coordination cost is justified.

## Output Contract

Boundary decision with ownership, contracts, consistency model, failure isolation, deployment needs, and extraction path.

## Quality Gates

- Are ownership, latency budgets, retries, and versioning explicit?
- Can the team deploy, observe, and recover the service independently?
- The boundary has a justified benefit that survives its migration and operational cost.

## Failure Modes

- Distributed monolith: test runtime coupling.
- Shared database silently defeats ownership: define allowed access contracts.

## Handoffs

Backend and Database Engineers assess consistency; DevOps validates independent operation; Security reviews trust changes.
