# Infrastructure Security

## Purpose

Reduce attack paths through hosts, networks, identities, and deployment infrastructure.

## When to Use

Infrastructure is provisioned or exposure and privilege change.

## When Not to Use

Do not harden blindly in ways that break recovery or unrelated services.

## Required Inputs

### Required

Topology, asset sensitivity, identities, network paths, current configuration, and authorized scope.

### Helpful

Architecture and code, data classification, actors, trust boundaries, exposure, existing controls, and authorized test scope.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Threat-based infrastructure findings or control plan with access, exposure, patching, logging, and recovery checks.

## Operating Principles

Separate confirmed vulnerability from suspected weakness; prioritize reachable impact and never include usable secrets or unnecessary exploit detail in public artifacts.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect actual listeners, ingress/egress, identities, admin paths, and shared failure domains.
2. Map reachable assets and excessive privileges to plausible attacker paths.
3. Choose least-privilege, segmentation, configuration, update, and detection controls proportionate to exposure.
4. Validate intended access and denied paths while preserving emergency recovery.

## Decision Rules

- If a firewall or identity change may lock out operators, establish a tested recovery path first.
- If a service is not required externally, remove exposure only after confirming its consumers and authority.

## Validation

- Are administrative paths constrained and monitored?
- Do controls preserve needed service behavior and recoverability?

## Common Failure Modes

- Port closure breaks a dependency: inspect consumers.
- Patch level used as sole risk measure: consider reachability and privilege.

## Escalation and Collaboration

DevOps implements changes; service owners confirm consumers; incident response handles active compromise.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
