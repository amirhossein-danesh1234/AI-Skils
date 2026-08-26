# Infrastructure Security

Context: [Security Engineer](README.md).

## Purpose

Reduce attack paths through hosts, networks, identities, and deployment infrastructure.

## Activate When

Infrastructure is provisioned or exposure and privilege change.

## Do Not Use When

Do not harden blindly in ways that break recovery or unrelated services.

## Required Context

**Needed:** Actual topology, identities, listeners, asset sensitivity, and authorized boundary.

**Can be deferred or bounded:** A hardening proposal may be read-only; access/firewall changes require preservation of recovery and consumer paths.

## Workflow

1. Inspect actual listeners, ingress/egress, identities, admin paths, and shared failure domains.
2. Map reachable assets and excessive privileges to plausible attacker paths.
3. Choose least-privilege, segmentation, configuration, update, and detection controls proportionate to exposure.
4. Validate intended access and denied paths while preserving emergency recovery.

## Reachability and Privilege

Trace ingress to exposed service, service identity to secrets/data, and administrative access to control plane. Prioritize paths with credible impact rather than checklist count. Test denied paths as well as required ones; verify emergency access remains controlled and recoverable.

## Decision Rules

- If a firewall or identity change may lock out operators, establish a tested recovery path first.
- If a service is not required externally, remove exposure only after confirming its consumers and authority.

## Output Contract

Threat-based infrastructure findings or control plan with access, exposure, patching, logging, and recovery checks.

## Quality Gates

- Are administrative paths constrained and monitored?
- Do controls preserve needed service behavior and recoverability?
- A control reduces the documented attack path without silently breaking essential service or recovery.

## Failure Modes

- Port closure breaks a dependency: inspect consumers.
- Patch level used as sole risk measure: consider reachability and privilege.

## Handoffs

DevOps implements changes; service owners confirm consumers; incident response handles active compromise.
