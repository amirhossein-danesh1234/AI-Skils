# Authentication

Context: [Backend Engineer](README.md).

## Purpose

Implement identity verification and session lifecycle using established mechanisms.

## Activate When

A service needs login, session, token, recovery, or identity-provider integration.

## Do Not Use When

Authorization determines allowed actions; do not invent custom cryptography or identity proof.

## Required Context

**Needed:** Credential protocol/provider, clients, identity lifecycle, and recovery policy.

**Can be deferred or bounded:** Use maintained mechanisms; no need to invent a new token format when an existing session model is adequate.

## Workflow

1. Inspect existing identity providers and supported framework mechanisms before adding custom code.
2. Define login, renewal, logout, recovery, and credential-change flows for each client type.
3. Identify the credential protocol. Validate signed self-contained tokens with maintained libraries and applicable signature, issuer, audience, and time checks; validate opaque sessions or reference tokens through the trusted session store or authorized introspection, including active state, expiry, revocation, and intended scope/resource.
4. Test invalid, expired, revoked, replayed, and interrupted flows; redact credentials from diagnostics.

## Credential-Type Validation

Do not force JWT or another signed-token format onto a correct opaque-session design. First establish which party issues the credential, which party validates it, and how current validity and permissions are obtained. For signed credentials, cryptographic verification and applicable claim checks must use trusted configuration and maintained libraries. For opaque credentials, use the trusted session mechanism or an authenticated, protected introspection channel; a syntactically plausible identifier is not proof of an active session.

Define validation-cache lifetime, revocation delay, identity-provider unavailability, and safe failure behavior according to the actual protocol and risk. Keep identity verification separate from authorization of the requested resource. [OAuth token introspection, RFC 7662](https://www.rfc-editor.org/rfc/rfc7662.html), is a primary reference for OAuth reference-token validation, not a requirement that every local session system use OAuth.

## Session Boundary

Specify session creation/rotation, login CSRF or request-origin controls where applicable, cookie attributes for browser sessions, and logout/recovery consequences. Test old sessions after credential change and provider outage. Keep authentication cache lifetime consistent with the promised revocation behavior.

## Decision Rules

- If a managed or framework mechanism meets requirements, prefer it over custom credential handling.
- If account recovery bypasses stronger controls, treat it as part of the authentication threat model.

## Output Contract

Authentication implementation or design with lifecycle, secure storage, expiry, revocation, recovery, and tests.

## Quality Gates

- Do logout, revocation, and credential changes have explicit session consequences?
- Are secrets and tokens absent from logs, URLs, and unsafe client storage?
- The implementation validates the actual credential protocol and does not confuse decoding with trust.

## Failure Modes

- Decoding or merely finding a token mistaken for validation: verify trust and current validity according to its actual protocol.
- Recovery weaker than login: review the whole lifecycle.

## Handoffs

Security Engineer independently reviews identity threats; Frontend Engineer implements client flow; DevOps manages secrets and configuration.
