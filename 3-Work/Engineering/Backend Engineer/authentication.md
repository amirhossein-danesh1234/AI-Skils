# Authentication

## Purpose

Implement identity verification and session lifecycle using established mechanisms.

## When to Use

A service needs login, session, token, recovery, or identity-provider integration.

## When Not to Use

Authorization determines allowed actions; do not invent custom cryptography or identity proof.

## Required Inputs

### Required

Identity requirements, trusted provider, clients, runtime, session model, threat context, and recovery policy.

### Helpful

Repository, runtime, business rules, contracts, data model, identity context, failure evidence, and deployment constraints.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Authentication implementation or design with lifecycle, secure storage, expiry, revocation, recovery, and tests.

## Operating Principles

Enforce invariants at the authoritative boundary, make retries safe, redact sensitive diagnostics, and verify persisted outcomes rather than status codes alone.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect existing identity providers and supported framework mechanisms before adding custom code.
2. Define login, renewal, logout, recovery, and credential-change flows for each client type.
3. Identify the credential protocol. Validate signed self-contained tokens with maintained libraries and applicable signature, issuer, audience, and time checks; validate opaque sessions or reference tokens through the trusted session store or authorized introspection, including active state, expiry, revocation, and intended scope/resource.
4. Test invalid, expired, revoked, replayed, and interrupted flows; redact credentials from diagnostics.

## Credential-Type Validation

Do not force JWT or another signed-token format onto a correct opaque-session design. First establish which party issues the credential, which party validates it, and how current validity and permissions are obtained. For signed credentials, cryptographic verification and applicable claim checks must use trusted configuration and maintained libraries. For opaque credentials, use the trusted session mechanism or an authenticated, protected introspection channel; a syntactically plausible identifier is not proof of an active session.

Define validation-cache lifetime, revocation delay, identity-provider unavailability, and safe failure behavior according to the actual protocol and risk. Keep identity verification separate from authorization of the requested resource. [OAuth token introspection, RFC 7662](https://www.rfc-editor.org/rfc/rfc7662.html), is a primary reference for OAuth reference-token validation, not a requirement that every local session system use OAuth.

## Decision Rules

- If a managed or framework mechanism meets requirements, prefer it over custom credential handling.
- If account recovery bypasses stronger controls, treat it as part of the authentication threat model.

## Validation

- Do logout, revocation, and credential changes have explicit session consequences?
- Are secrets and tokens absent from logs, URLs, and unsafe client storage?

## Common Failure Modes

- Decoding or merely finding a token mistaken for validation: verify trust and current validity according to its actual protocol.
- Recovery weaker than login: review the whole lifecycle.

## Escalation and Collaboration

Security Engineer independently reviews identity threats; Frontend Engineer implements client flow; DevOps manages secrets and configuration.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
