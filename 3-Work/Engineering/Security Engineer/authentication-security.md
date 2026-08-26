# Authentication Security

Context: [Security Engineer](README.md).

## Purpose

Evaluate the full identity and session lifecycle against realistic account threats.

## Activate When

Login, recovery, tokens, federation, or session controls change.

## Do Not Use When

Backend [authentication.md](../Backend%20Engineer/authentication.md) implements identity; this skill independently challenges its security.

## Required Context

**Needed:** Actual credential/session protocol, recovery flows, provider configuration, and test identities.

**Can be deferred or bounded:** Implementation details come from Backend authentication; this review independently challenges bypasses and revocation.

## Workflow

1. Map trust in credentials, identity providers, tokens, browsers, and recovery channels.
2. Inspect validation, anti-enumeration behavior, rate controls, session fixation, and token storage.
3. Test invalid, expired, revoked, and replayed credentials in a safe scope. Apply malformed-signature and wrong-issuer/audience tests to protocols where those claims exist; test lookup or introspection failure and stale validity for opaque credentials.
4. Review recovery and account changes for bypasses and define compromise containment.

## Protocol-Specific Challenge

For signed tokens, test applicable signature/issuer/audience/time validation; for opaque sessions, test trusted lookup/introspection, expired/revoked status, and stale caches. Attack the recovery and account-change path as well as login. Inspect browser origin protections and session fixation where applicable.

## Decision Rules

- If recovery defeats stronger login controls, treat recovery as the weakest identity path.
- If a signed self-contained token lacks required signature or applicable claim validation, reject that design. For opaque sessions or reference tokens, require trusted lookup or authorized introspection and protocol-appropriate active, expiry, revocation, scope, and resource checks instead of demanding embedded claims.

## Output Contract

Identity threat findings and control requirements covering login, recovery, renewal, logout, and compromise response.

## Quality Gates

- Do all identity paths enforce the intended assurance level?
- Are revocation limitations and session consequences documented and tested?
- The weakest identity path meets the intended assurance and revocation behavior is measured, not assumed.

## Failure Modes

- MFA presence assumed sufficient: inspect bypass and recovery.
- Authentication logs leak credentials: verify redaction.

## Handoffs

Backend Engineer implements fixes; Frontend Engineer secures client handling; DevOps manages identity configuration.
