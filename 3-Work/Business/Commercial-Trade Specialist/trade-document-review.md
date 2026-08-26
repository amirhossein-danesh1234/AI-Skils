# Trade Document Review

Context: [Commercial-Trade Specialist](README.md).

## Purpose

Check trade documents for consistency, completeness, and operational consequences.

## Activate When

Invoices, orders, packing lists, transport, insurance, or payment documents need review.

## Do Not Use When

Do not certify authenticity or legal sufficiency without authority and expertise.

## Required Context

**Needed:** Full document set, authoritative contract, goods details, and applicable requirements.

**Can be deferred or bounded:** Incomplete sets permit a discrepancy report, not authenticity or legal sufficiency certification.

## Workflow

1. Establish the authoritative contract and required document set.
2. Compare parties, goods, quantities, units, values, currency, dates, locations, and references across documents.
3. Check delivery rule, transport, insurance, origin, and payment conditions for consistency.
4. Prioritize discrepancies that could block payment, clearance, delivery, or claims.

## Cross-Document Key

Compare parties, identifiers, quantities/units, goods description, currency/value, dates, named places, and references. Rank mismatches by payment, clearance, delivery, or claims consequence. Corrections come from the responsible issuer; do not silently normalize a material conflict in a summary.

## Decision Rules

- If documents disagree on a material field, do not silently normalize it; obtain correction from the responsible issuer.
- If authenticity is uncertain, verify through an independent trusted channel.

## Output Contract

Discrepancy report with field, conflicting sources, consequence, correction owner, and unresolved verification.

## Quality Gates

- Are material cross-document fields reconciled?
- Are corrections traceable and approved by the appropriate party?
- Every material discrepancy has an owner and a hold/release implication.

## Failure Modes

- Formatting review misses commercial mismatch: compare obligations.
- Document existence implies authenticity: verify when material.

## Handoffs

Supplier, carrier, bank, customs broker, or legal specialist resolves their respective document issues.
