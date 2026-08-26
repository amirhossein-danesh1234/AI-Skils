# API Integration

Context: [Frontend Engineer](README.md).

## Purpose

Connect the UI to a server contract with correct data and failure behavior.

## Activate When

A frontend needs to load or mutate remote data.

## Do Not Use When

Do not invent backend fields, treat UI authorization as security, or retry unsafe mutations blindly.

## Required Context

**Needed:** Endpoint contract, identity mechanism, error states, and consumer behavior.

**Can be deferred or bounded:** If the API is unavailable, use explicit contract fixtures and label live integration unverified.

## Workflow

1. Inspect actual endpoints, payloads, identity handling, pagination, and version compatibility.
2. Map server data to UI needs without leaking transport details through every component.
3. Handle timeouts, cancellation, unauthorized responses, empty results, and validation errors.
4. Define cache invalidation and mutation retry behavior; verify persisted outcomes after refresh.

## Race and Persistence

Test an earlier slow response arriving after a later request, a navigation during mutation, and a refresh after reported success. Keep transport failure separate from domain rejection and outcome unknown. Invalidate only the relevant cached state and never rely on hiding a control for server authorization.

## Decision Rules

- If a mutation lacks idempotency guarantees, do not automatically repeat it after ambiguous failure.
- If the contract differs from the specification, surface the discrepancy rather than guessing.

## Output Contract

Integration with typed or validated boundaries, loading/error states, cancellation, cache behavior, and contract tests.

## Quality Gates

- Do successful and failed flows produce correct visible and persisted state?
- Are credentials excluded from URLs, logs, and unintended storage?
- The UI cannot overwrite newer state with a stale response or duplicate an unsafe mutation.

## Failure Modes

- HTTP success treated as business success: inspect outcome fields.
- Stale cache hides a failed mutation: verify authoritative refresh.

## Handoffs

Backend Engineer resolves contract issues; Security reviews token handling; QA tests end-to-end behavior.
