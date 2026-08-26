# Reliability Review

## Purpose

Assess whether a service can meet agreed user outcomes under expected failure and load.

## When to Use

A service needs readiness review or recurring incidents suggest systemic weakness.

## When Not to Use

Do not equate uptime percentage with complete reliability or demand arbitrary enterprise rigor.

## Required Inputs

### Required

Service objectives, incidents, topology, load, dependencies, recovery tests, and operator capacity.

### Helpful

Actual infrastructure and listeners, release process, identities, dependencies, service objectives, secrets handling, and current incident state.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Reliability assessment with evidence, failure scenarios, gaps, priorities, and accepted residual risk.

## Operating Principles

Inspect before mutation; use immutable or traceable releases, least privilege, explicit stop conditions, and real service checks.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect user-facing success, latency, freshness, and correctness objectives.
2. Walk dependency failure, overload, deployment error, data loss, and operator response scenarios.
3. Compare monitoring and recovery evidence with the objectives and error tolerance.
4. Prioritize the smallest changes that reduce dominant risk or operational toil.

## Decision Rules

- If an objective has no measurement, mark compliance unknown.
- If a dependency exceeds the service’s tolerance, add containment or renegotiate the objective.

## Validation

- Are critical scenarios supported by tests or clearly marked assumptions?
- Can the actual team operate the proposed controls?

## Common Failure Modes

- Availability target copied from peers: ground it in user needs.
- Redundancy assumed independent: inspect shared failure domains.

## Escalation and Collaboration

Architect addresses structural risks; Database Engineer checks recovery; QA validates failure tests; owner accepts risk.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
