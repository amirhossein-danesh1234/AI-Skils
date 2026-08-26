# OWASP Review

## Purpose

Use applicable OWASP guidance to structure a scoped control review.

## When to Use

A team requests an OWASP-aligned assessment or needs a recognized control baseline.

## When Not to Use

A Top Ten checklist is not a complete test standard or certification.

## Required Inputs

### Required

Application scope, technology/version, threat model, assurance needs, and selected OWASP publication/version.

### Helpful

Architecture and code, data classification, actors, trust boundaries, exposure, existing controls, and authorized test scope.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Versioned applicability map with tested controls, findings, evidence, exclusions, and remediation priorities.

## Operating Principles

Separate confirmed vulnerability from suspected weakness; prioritize reachable impact and never include usable secrets or unnecessary exploit detail in public artifacts.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Select a relevant current OWASP source, such as ASVS for verifiable application controls, and record its version.
2. Map controls to actual assets and attack surfaces; justify non-applicable items.
3. Inspect implementation and run safe tests for the selected controls.
4. Report evidence and gaps without turning the checklist into a blanket security claim.

## Decision Rules

- If a guidance item is too broad to test, translate it into a system-specific verification condition.
- If threat analysis reveals a risk outside the checklist, include it rather than ignoring it.

## Validation

- Are requirement identifiers and versions accurate?
- Can another reviewer distinguish tested, failed, untested, and not-applicable controls?

## Common Failure Modes

- Framework name used as assurance: show evidence.
- Outdated version silently reused: verify and record source.

## Escalation and Collaboration

Security-review.md handles findings; threat-modeling.md supplies context; engineers and QA validate controls.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
