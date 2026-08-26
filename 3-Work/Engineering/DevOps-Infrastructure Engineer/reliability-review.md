# Reliability Review

Context: [DevOps-Infrastructure Engineer](README.md).

## Purpose

Assess whether a service can meet agreed user outcomes under expected failure and load.

## Activate When

A service needs readiness review or recurring incidents suggest systemic weakness.

## Do Not Use When

Do not equate uptime percentage with complete reliability or demand arbitrary enterprise rigor.

## Required Context

**Needed:** Service outcomes, topology, incidents, load evidence, and recovery capability.

**Can be deferred or bounded:** Unknown objectives prevent a compliance conclusion but still permit a risk assessment.

## Workflow

1. Inspect user-facing success, latency, freshness, and correctness objectives.
2. Walk dependency failure, overload, deployment error, data loss, and operator response scenarios.
3. Compare monitoring and recovery evidence with the objectives and error tolerance.
4. Prioritize the smallest changes that reduce dominant risk or operational toil.

## Failure Envelope

Walk dependency slowness, overload, bad deployment, data loss, and operator unavailability. Check shared failure domains, retry amplification, degradation, and tested recovery. Prefer the smallest intervention that reduces the dominant user risk rather than adding redundancy that shares the same dependency.

## Decision Rules

- If an objective has no measurement, mark compliance unknown.
- If a dependency exceeds the service’s tolerance, add containment or renegotiate the objective.

## Output Contract

Reliability assessment with evidence, failure scenarios, gaps, priorities, and accepted residual risk.

## Quality Gates

- Are critical scenarios supported by tests or clearly marked assumptions?
- Can the actual team operate the proposed controls?
- The actual team can detect, contain, and recover within the claimed service expectations.

## Failure Modes

- Availability target copied from peers: ground it in user needs.
- Redundancy assumed independent: inspect shared failure domains.

## Handoffs

Architect addresses structural risks; Database Engineer checks recovery; QA validates failure tests; owner accepts risk.
