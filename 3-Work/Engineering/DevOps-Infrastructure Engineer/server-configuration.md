# Server Configuration

Context: [DevOps-Infrastructure Engineer](README.md).

## Purpose

Configure a host while preserving access, existing services, and recoverability.

## Activate When

A server needs a scoped setup or configuration change.

## Do Not Use When

Do not reconfigure unrelated services, firewall rules, or remote access without authority.

## Required Context

**Needed:** Exact host, mandate, baseline services/listeners, access path, and recovery route.

**Can be deferred or bounded:** Optional tuning can wait; any possible remote lockout requires a recovery path before mutation.

## Workflow

1. Inspect identity, resources, services, ports, firewall, storage, and current access before mutation.
2. Resolve exact files and service targets and check for conflicts with existing workloads.
3. Apply minimal changes with recoverable configuration copies and validated syntax.
4. Verify service behavior and remote access from an appropriate independent path.

## Change Envelope

Record the precise file/service and expected difference, validate syntax, and keep a recoverable configuration. Check service consumers before changing ports or firewall rules. Verify from an independent path that remote access and unrelated services remain intact, then test persistence across the relevant restart.

## Decision Rules

- If a change could lock out remote access, establish a recovery path before applying it.
- If a required port is occupied, investigate ownership rather than stopping the existing service.

## Output Contract

Scoped configuration change with baseline, backup, conflict checks, verification, and reversal instructions.

## Quality Gates

- Do intended services work and unrelated listeners remain intact?
- Are permissions, startup persistence, and rollback tested where feasible?
- The intended application works and no unrelated listener or access path was silently disrupted.

## Failure Modes

- Blind setup script overwrites state: inspect first.
- Port open treated as application success: exercise the service.

## Handoffs

Security reviews exposure; application owner confirms behavior; hosting operator handles access recovery.
