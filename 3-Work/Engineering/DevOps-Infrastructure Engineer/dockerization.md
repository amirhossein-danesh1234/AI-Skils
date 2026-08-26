# Dockerization

Context: [DevOps-Infrastructure Engineer](README.md).

## Purpose

Package an application with a reproducible runtime and safe container behavior.

## Activate When

A service needs a container image or an existing image is unreliable or oversized.

## Do Not Use When

Do not assume containers remove host, network, or secret-management risks.

## Required Context

**Needed:** Runtime/build contract, startup/shutdown behavior, writable state, and deployment target.

**Can be deferred or bounded:** Image size optimization can wait until correctness and secret exclusion are verified.

## Workflow

1. Inspect application startup, dependency locking, generated assets, and required writable paths.
2. Separate build and runtime concerns and exclude secrets and unnecessary context.
3. Define user privileges, signals, graceful shutdown, resource needs, and persistent data boundaries.
4. Build and run representative operations, including restart and dependency failure.

## Runtime Contract

Test signal handling, graceful termination, non-root writable paths, dependency readiness, and replacement with persistent data intact. Keep build-time credentials out of layers and context. A health endpoint should distinguish liveness from readiness when restarting an unhealthy dependency would worsen an outage.

## Decision Rules

- If data must survive replacement, place it in an explicitly managed persistent store.
- If a base image or dependency is unpinned, define how reproducibility and updates are controlled.

## Output Contract

Container build and runtime specification with minimal privileges, health behavior, persistence, and tests.

## Quality Gates

- Does the image run the real application without hidden host assumptions?
- Are secrets absent from image layers and build context?
- The shipped image runs without hidden local mounts or credentials and survives a representative restart.

## Failure Modes

- Works only with local mounts: test the shipped image.
- Root privileges used by default: minimize and justify.

## Handoffs

Backend Engineer validates runtime behavior; Security reviews image exposure; [deployment-design.md](deployment-design.md) governs rollout.
