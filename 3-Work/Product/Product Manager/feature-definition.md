# Feature Definition

Context: [Product Manager](README.md).

## Purpose

Define a bounded product capability justified by an accepted problem.

## Activate When

A solution path is selected and the team needs to agree what capability is intended.

## Do Not Use When

Use [problem-definition.md](problem-definition.md) for unclear needs and [prd-writing.md](prd-writing.md) for a detailed delivery specification.

## Required Context

**Needed:** Accepted problem, affected user, desired outcome, and constraints.

**Can be deferred or bounded:** A complete PRD is not required for a brief; consequential permission, money, and lifecycle questions must be flagged.

## Workflow

1. Inspect current behavior and existing capabilities that might satisfy the need.
2. Define the smallest coherent user outcome, including who can initiate and complete it.
3. Map normal, empty, error, permission, and recovery states at capability level.
4. Identify integrations and policy decisions; compare the benefit with maintenance and operational burden.

## Smallest Coherent Capability

Define who starts the capability, the authoritative state it changes, and what demonstrates success. List included and excluded scenarios rather than broad feature nouns. Compare a manual workaround or extension of existing behavior with a new feature before choosing the delivery slice.

## Decision Rules

- If the capability requires unresolved policy, mark the decision owner and block only the affected scope.
- If an existing capability can be adjusted, prefer reuse unless it creates greater complexity.

## Output Contract

Feature brief with scenarios, scope, exclusions, states, dependencies, success signals, and open decisions.

## Quality Gates

- Can the feature be explained without prescribing implementation?
- Are exclusions and failure behavior sufficient to prevent scope ambiguity?
- The brief includes failure/recovery and prevents two incompatible interpretations of scope.

## Failure Modes

- Feature list without outcome: anchor to a scenario.
- Happy path only: include recovery and permission states.

## Handoffs

UX Designer owns interaction detail; Architect checks structural impact; Product Analyst defines measurement.
