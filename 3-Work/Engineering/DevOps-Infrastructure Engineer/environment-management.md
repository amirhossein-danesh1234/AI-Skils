# Environment Management

Context: [DevOps-Infrastructure Engineer](README.md).

## Purpose

Keep configuration and secrets consistent with each environment’s purpose.

## Activate When

Local, test, staging, or production behavior differs unexpectedly or new environments are needed.

## Do Not Use When

Do not copy production secrets or personal data into less protected environments.

## Required Context

**Needed:** Configuration sources/precedence, environment roles, endpoints, and secret references.

**Can be deferred or bounded:** Do not print values to compare environments; names and redacted source metadata usually suffice.

## Workflow

1. Inspect configuration sources and precedence without printing secret values.
2. Classify public settings, secrets, and environment-specific dependencies.
3. Validate required values at startup and ensure dangerous defaults cannot silently apply in production.
4. Compare environments for intentional differences and test configuration changes before promotion.

## Effective Configuration

Trace what configuration the process actually uses after defaults, files, environment, and runtime overrides. Validate dangerous missing values at startup and verify staging cannot call live payment, messaging, or production data endpoints inadvertently. Test change and rollback without exposing secrets.

## Decision Rules

- If a missing value can redirect traffic or disable protection, fail clearly rather than use a permissive default.
- If test data contains sensitive production information, require approved minimization and access controls.

## Output Contract

Environment contract with required values, safe defaults, validation, ownership, and drift checks.

## Quality Gates

- Are effective values traceable to their source without disclosure?
- Can drift be detected and corrected reproducibly?
- Environment labels agree with actual destinations, identities, and data isolation.

## Failure Modes

- Environment names imply safety: verify actual endpoints.
- Secrets embedded in examples: use non-secret references.

## Handoffs

Security reviews secret policy; engineers define configuration semantics; Database Engineer validates data isolation.
