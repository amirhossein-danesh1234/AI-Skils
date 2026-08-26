# Dockerization

## Purpose

Package an application with a reproducible runtime and safe container behavior.

## When to Use

A service needs a container image or an existing image is unreliable or oversized.

## When Not to Use

Do not assume containers remove host, network, or secret-management risks.

## Required Inputs

### Required

Application runtime/version, build process, dependencies, entrypoint, storage, and deployment target.

### Helpful

Actual infrastructure and listeners, release process, identities, dependencies, service objectives, secrets handling, and current incident state.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Container build and runtime specification with minimal privileges, health behavior, persistence, and tests.

## Operating Principles

Inspect before mutation; use immutable or traceable releases, least privilege, explicit stop conditions, and real service checks.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect application startup, dependency locking, generated assets, and required writable paths.
2. Separate build and runtime concerns and exclude secrets and unnecessary context.
3. Define user privileges, signals, graceful shutdown, resource needs, and persistent data boundaries.
4. Build and run representative operations, including restart and dependency failure.

## Decision Rules

- If data must survive replacement, place it in an explicitly managed persistent store.
- If a base image or dependency is unpinned, define how reproducibility and updates are controlled.

## Validation

- Does the image run the real application without hidden host assumptions?
- Are secrets absent from image layers and build context?

## Common Failure Modes

- Works only with local mounts: test the shipped image.
- Root privileges used by default: minimize and justify.

## Escalation and Collaboration

Backend Engineer validates runtime behavior; Security reviews image exposure; deployment-design.md governs rollout.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
