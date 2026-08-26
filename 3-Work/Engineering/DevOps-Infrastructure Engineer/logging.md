# Logging

Context: [DevOps-Infrastructure Engineer](README.md).

## Purpose

Design diagnostic and audit events that explain behavior without exposing sensitive data.

## Activate When

Troubleshooting or audit needs are not supported by existing logs.

## Do Not Use When

Do not log full payloads, tokens, or personal data by default.

## Required Context

**Needed:** Operational/audit questions, event paths, data sensitivity, and retention needs.

**Can be deferred or bounded:** Log platform choice can be deferred; field necessity and sensitive-data exclusion cannot.

## Workflow

1. Inspect which operational questions cannot currently be answered.
2. Define structured events at meaningful transitions with stable correlation identifiers.
3. Separate audit requirements from debug detail and redact or omit sensitive values.
4. Test searchability, volume, failure behavior, and access restrictions.

## Diagnostic Query Test

Write the query an operator needs to answer, then design only the events and fields required. Carry request/job/operation correlation without logging secrets or entire payloads. Distinguish audit integrity requirements from debug sampling, and test what happens when the log sink fails.

## Decision Rules

- If a field is not necessary for diagnosis or audit, omit it rather than collect by default.
- If log delivery fails, define whether the business operation may continue based on its risk and obligations.

## Output Contract

Event schema, levels, correlation, redaction, access, retention, and verification plan.

## Quality Gates

- Can a failed operation be traced without reconstructing secrets?
- Are retention and access compatible with the data’s sensitivity?
- A failed operation can be reconstructed from minimal permitted evidence.

## Failure Modes

- Verbose logs hide signal: log meaningful transitions.
- Redaction only at display: prevent sensitive ingestion where possible.

## Handoffs

Security approves sensitive handling; Backend Engineer defines event semantics; Operations uses diagnostic queries.
