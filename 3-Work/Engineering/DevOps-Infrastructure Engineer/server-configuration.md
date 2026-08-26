# Server Configuration

## Purpose

Configure a host while preserving access, existing services, and recoverability.

## When to Use

A server needs a scoped setup or configuration change.

## When Not to Use

Do not reconfigure unrelated services, firewall rules, or remote access without authority.

## Required Inputs

### Required

Target host, authorized scope, current listeners/services, OS/version, access method, and recovery path.

### Helpful

Actual infrastructure and listeners, release process, identities, dependencies, service objectives, secrets handling, and current incident state.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Scoped configuration change with baseline, backup, conflict checks, verification, and reversal instructions.

## Operating Principles

Inspect before mutation; use immutable or traceable releases, least privilege, explicit stop conditions, and real service checks.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect identity, resources, services, ports, firewall, storage, and current access before mutation.
2. Resolve exact files and service targets and check for conflicts with existing workloads.
3. Apply minimal changes with recoverable configuration copies and validated syntax.
4. Verify service behavior and remote access from an appropriate independent path.

## Decision Rules

- If a change could lock out remote access, establish a recovery path before applying it.
- If a required port is occupied, investigate ownership rather than stopping the existing service.

## Validation

- Do intended services work and unrelated listeners remain intact?
- Are permissions, startup persistence, and rollback tested where feasible?

## Common Failure Modes

- Blind setup script overwrites state: inspect first.
- Port open treated as application success: exercise the service.

## Escalation and Collaboration

Security reviews exposure; application owner confirms behavior; hosting operator handles access recovery.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
