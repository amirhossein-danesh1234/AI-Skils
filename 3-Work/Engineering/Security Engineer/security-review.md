# Security Review

## Purpose

Assess a bounded implementation or design for evidence-backed security risk.

## When to Use

A feature, release, or system change needs security scrutiny.

## When Not to Use

Do not call a system secure because no issue was found within limited scope.

## Required Inputs

### Required

Authorized scope, architecture, code/configuration, threat context, data sensitivity, and available test environment.

### Helpful

Architecture and code, data classification, actors, trust boundaries, exposure, existing controls, and authorized test scope.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Review report with coverage, confirmed and suspected findings, severity rationale, remediation, and residual risk.

## Operating Principles

Separate confirmed vulnerability from suspected weakness; prioritize reachable impact and never include usable secrets or unnecessary exploit detail in public artifacts.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Establish test permission and inspect the changed attack surface and critical assets.
2. Trace trust boundaries and compare intended controls with actual enforcement.
3. Use safe code/configuration review and proportionate tests to validate reachable weaknesses.
4. Prioritize remediation and retest the affected path, including likely alternate entry points.

## Decision Rules

- If validation would risk production or third parties, stop and request a safe authorized method.
- If a finding lacks evidence, label it suspected and state the verification needed.

## Validation

- Are severity and reachability explained in system context?
- Are scope gaps and untested controls explicit?

## Common Failure Modes

- Checklist completion becomes assurance: report evidence and limits.
- Exploit detail exposes secrets: minimize sensitive reproduction data.

## Escalation and Collaboration

Implementation owners remediate; QA tests regressions; business owner accepts residual risk.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
