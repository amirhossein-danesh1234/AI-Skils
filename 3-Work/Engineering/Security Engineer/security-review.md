# Security Review

Context: [Security Engineer](README.md).

## Purpose

Assess a bounded implementation or design for evidence-backed security risk.

## Activate When

A feature, release, or system change needs security scrutiny.

## Do Not Use When

Do not call a system secure because no issue was found within limited scope.

## Required Context

**Needed:** Bounded authorized scope, changed attack surface, asset sensitivity, and evidence.

**Can be deferred or bounded:** Absent safe testing access limits conclusions; do not run intrusive validation outside the mandate.

## Workflow

1. Establish test permission and inspect the changed attack surface and critical assets.
2. Trace trust boundaries and compare intended controls with actual enforcement.
3. Use safe code/configuration review and proportionate tests to validate reachable weaknesses.
4. Prioritize remediation and retest the affected path, including likely alternate entry points.

## Finding Evidence

Record asset, actor prerequisites, reachable path, impact, control failure, and sanitized proof. Distinguish confirmed from suspected findings and explain residual risk after correction. Retest alternate paths so a fix to one endpoint is not mistaken for eliminating the class.

## Decision Rules

- If validation would risk production or third parties, stop and request a safe authorized method.
- If a finding lacks evidence, label it suspected and state the verification needed.

## Output Contract

Review report with coverage, confirmed and suspected findings, severity rationale, remediation, and residual risk.

## Quality Gates

- Are severity and reachability explained in system context?
- Are scope gaps and untested controls explicit?
- A clean limited review is not presented as a guarantee that the system is secure.

## Failure Modes

- Checklist completion becomes assurance: report evidence and limits.
- Exploit detail exposes secrets: minimize sensitive reproduction data.

## Handoffs

Implementation owners remediate; QA tests regressions; business owner accepts residual risk.
