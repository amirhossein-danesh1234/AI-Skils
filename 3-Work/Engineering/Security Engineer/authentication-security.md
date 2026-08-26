# Authentication Security

## Purpose

Evaluate the full identity and session lifecycle against realistic account threats.

## When to Use

Login, recovery, tokens, federation, or session controls change.

## When Not to Use

Backend authentication.md implements identity; this skill independently challenges its security.

## Required Inputs

### Required

Identity flows, provider configuration, clients, session policy, threat actors, and authorized test accounts.

### Helpful

Architecture and code, data classification, actors, trust boundaries, exposure, existing controls, and authorized test scope.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Identity threat findings and control requirements covering login, recovery, renewal, logout, and compromise response.

## Operating Principles

Separate confirmed vulnerability from suspected weakness; prioritize reachable impact and never include usable secrets or unnecessary exploit detail in public artifacts.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Map trust in credentials, identity providers, tokens, browsers, and recovery channels.
2. Inspect validation, anti-enumeration behavior, rate controls, session fixation, and token storage.
3. Test invalid, expired, revoked, and replayed credentials in a safe scope. Apply malformed-signature and wrong-issuer/audience tests to protocols where those claims exist; test lookup or introspection failure and stale validity for opaque credentials.
4. Review recovery and account changes for bypasses and define compromise containment.

## Credential-Type Validation

Do not force JWT or another signed-token format onto a correct opaque-session design. First establish which party issues the credential, which party validates it, and how current validity and permissions are obtained. For signed credentials, cryptographic verification and applicable claim checks must use trusted configuration and maintained libraries. For opaque credentials, use the trusted session mechanism or an authenticated, protected introspection channel; a syntactically plausible identifier is not proof of an active session.

Define validation-cache lifetime, revocation delay, identity-provider unavailability, and safe failure behavior according to the actual protocol and risk. Keep identity verification separate from authorization of the requested resource. [OAuth token introspection, RFC 7662](https://www.rfc-editor.org/rfc/rfc7662.html), is a primary reference for OAuth reference-token validation, not a requirement that every local session system use OAuth.

## Decision Rules

- If recovery defeats stronger login controls, treat recovery as the weakest identity path.
- If a signed self-contained token lacks required signature or applicable claim validation, reject that design. For opaque sessions or reference tokens, require trusted lookup or authorized introspection and protocol-appropriate active, expiry, revocation, scope, and resource checks instead of demanding embedded claims.

## Validation

- Do all identity paths enforce the intended assurance level?
- Are revocation limitations and session consequences documented and tested?

## Common Failure Modes

- MFA presence assumed sufficient: inspect bypass and recovery.
- Authentication logs leak credentials: verify redaction.

## Escalation and Collaboration

Backend Engineer implements fixes; Frontend Engineer secures client handling; DevOps manages identity configuration.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
