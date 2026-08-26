# CI CD

## Purpose

Build a repeatable pipeline that produces and promotes verifiable artifacts.

## When to Use

Manual build or release steps need reliable automation.

## When Not to Use

Do not grant broad credentials or execute untrusted contributions with privileged secrets.

## Required Inputs

### Required

Repository workflow, build/test commands, environments, artifact policy, and permissions.

### Helpful

Actual infrastructure and listeners, release process, identities, dependencies, service objectives, secrets handling, and current incident state.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Pipeline definition with validation, artifact identity, promotion gates, secrets handling, and failure recovery.

## Operating Principles

Inspect before mutation; use immutable or traceable releases, least privilege, explicit stop conditions, and real service checks.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect actual local build and test behavior and current deployment requirements.
2. Separate untrusted validation from privileged publication or deployment.
3. Build a traceable artifact once, record provenance, and promote it through appropriate checks.
4. Test failure paths, canceled runs, concurrency, and rollback to a known artifact.

## Decision Rules

- If pull-request code is untrusted, do not expose production secrets to its execution.
- If a pipeline rebuilds for each environment, verify that promoted content remains equivalent or prefer immutable promotion.

## Validation

- Can a release be traced to commit, dependencies, tests, and artifact?
- Do failed gates prevent deployment and preserve useful diagnostics?

## Common Failure Modes

- Green pipeline skips relevant tests: verify coverage.
- Mutable tags obscure deployed content: record immutable identity.

## Escalation and Collaboration

Security checks credentials and supply chain; engineers own test commands; release owner defines promotion authority.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
