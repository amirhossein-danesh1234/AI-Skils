# OWASP Review

Context: [Security Engineer](README.md).

## Purpose

Use applicable OWASP guidance to structure a scoped control review.

## Activate When

A team requests an OWASP-aligned assessment or needs a recognized control baseline.

## Do Not Use When

A Top Ten checklist is not a complete test standard or certification.

## Required Context

**Needed:** Application scope, selected publication/version, assurance needs, and evidence access.

**Can be deferred or bounded:** A baseline can be proposed; tested/not-tested/not-applicable states must remain distinct.

## Workflow

1. Select a relevant current OWASP source, such as ASVS for verifiable application controls, and record its version.
2. Map controls to actual assets and attack surfaces; justify non-applicable items.
3. Inspect implementation and run safe tests for the selected controls.
4. Report evidence and gaps without turning the checklist into a blanket security claim.

## Control Applicability

Map each selected requirement to a concrete component, test, and evidence result. Verify current requirement identifiers rather than copying an old checklist. Record justified non-applicability and threat-specific risks outside the framework; review coverage is not certification of the whole system.

## Decision Rules

- If a guidance item is too broad to test, translate it into a system-specific verification condition.
- If threat analysis reveals a risk outside the checklist, include it rather than ignoring it.

## Output Contract

Versioned applicability map with tested controls, findings, evidence, exclusions, and remediation priorities.

## Quality Gates

- Are requirement identifiers and versions accurate?
- Can another reviewer distinguish tested, failed, untested, and not-applicable controls?
- The report can identify exactly which controls were verified and which remain unknown.

## Failure Modes

- Framework name used as assurance: show evidence.
- Outdated version silently reused: verify and record source.

## Handoffs

[Security-review.md](security-review.md) handles findings; [threat-modeling.md](threat-modeling.md) supplies context; engineers and QA validate controls.
