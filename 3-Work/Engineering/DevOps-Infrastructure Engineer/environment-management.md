# Environment Management

## Purpose

Keep configuration and secrets consistent with each environment’s purpose.

## When to Use

Local, test, staging, or production behavior differs unexpectedly or new environments are needed.

## When Not to Use

Do not copy production secrets or personal data into less protected environments.

## Required Inputs

### Required

Configuration inventory, environment roles, secret stores, runtime, and deployment process.

### Helpful

Actual infrastructure and listeners, release process, identities, dependencies, service objectives, secrets handling, and current incident state.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Environment contract with required values, safe defaults, validation, ownership, and drift checks.

## Operating Principles

Inspect before mutation; use immutable or traceable releases, least privilege, explicit stop conditions, and real service checks.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect configuration sources and precedence without printing secret values.
2. Classify public settings, secrets, and environment-specific dependencies.
3. Validate required values at startup and ensure dangerous defaults cannot silently apply in production.
4. Compare environments for intentional differences and test configuration changes before promotion.

## Decision Rules

- If a missing value can redirect traffic or disable protection, fail clearly rather than use a permissive default.
- If test data contains sensitive production information, require approved minimization and access controls.

## Validation

- Are effective values traceable to their source without disclosure?
- Can drift be detected and corrected reproducibly?

## Common Failure Modes

- Environment names imply safety: verify actual endpoints.
- Secrets embedded in examples: use non-secret references.

## Escalation and Collaboration

Security reviews secret policy; engineers define configuration semantics; Database Engineer validates data isolation.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
