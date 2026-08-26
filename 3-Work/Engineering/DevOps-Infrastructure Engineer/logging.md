# Logging

## Purpose

Design diagnostic and audit events that explain behavior without exposing sensitive data.

## When to Use

Troubleshooting or audit needs are not supported by existing logs.

## When Not to Use

Do not log full payloads, tokens, or personal data by default.

## Required Inputs

### Required

Failure questions, request/job paths, data classification, log platform, and retention needs.

### Helpful

Actual infrastructure and listeners, release process, identities, dependencies, service objectives, secrets handling, and current incident state.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Event schema, levels, correlation, redaction, access, retention, and verification plan.

## Operating Principles

Inspect before mutation; use immutable or traceable releases, least privilege, explicit stop conditions, and real service checks.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect which operational questions cannot currently be answered.
2. Define structured events at meaningful transitions with stable correlation identifiers.
3. Separate audit requirements from debug detail and redact or omit sensitive values.
4. Test searchability, volume, failure behavior, and access restrictions.

## Decision Rules

- If a field is not necessary for diagnosis or audit, omit it rather than collect by default.
- If log delivery fails, define whether the business operation may continue based on its risk and obligations.

## Validation

- Can a failed operation be traced without reconstructing secrets?
- Are retention and access compatible with the data’s sensitivity?

## Common Failure Modes

- Verbose logs hide signal: log meaningful transitions.
- Redaction only at display: prevent sensitive ingestion where possible.

## Escalation and Collaboration

Security approves sensitive handling; Backend Engineer defines event semantics; Operations uses diagnostic queries.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
