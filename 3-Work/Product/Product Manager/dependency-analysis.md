# Dependency Analysis

Context: [Product Manager](README.md).

## Purpose

Identify product-level prerequisites and consequences before scope is committed.

## Activate When

A feature crosses teams, policies, data, vendors, or customer workflows.

## Do Not Use When

Project Manager manages delivery dependency dates; Architect owns technical coupling design.

## Required Context

**Needed:** Proposed scenarios and their required policies, capabilities, data, and parties.

**Can be deferred or bounded:** Dates may remain unknown during discovery; hard prerequisite ownership and acceptance cannot be implied.

## Workflow

1. Walk each user scenario and list inputs, approvals, capabilities, and downstream consumers.
2. Separate hard prerequisites from preferred sequence or assumed convenience.
3. Check circular dependencies and failure propagation into user outcomes.
4. Seek owner confirmation and compare decoupling, reduced scope, manual fallback, or delay.

## Dependency Necessity Test

Ask what fails if each dependency is absent. Classify it as hard prerequisite, quality constraint, convenience, or sequencing preference. Evaluate manual or narrower alternatives and record the new risks they introduce. Hand Project Manager only real delivery dependencies with a provider/consumer acceptance condition.

## Decision Rules

- If a prerequisite has no owner or feasible delivery path, mark affected scope unready.
- If a dependency can be removed without losing the outcome, prefer the simpler scope.

## Output Contract

Dependency map with type, owner, required condition, evidence, criticality, and fallback.

## Quality Gates

- Does every hard dependency have a verifiable completion condition?
- Are external lead times and policy approvals included?
- Removing a claimed prerequisite either preserves the outcome or has an explicit consequence.

## Failure Modes

- Only technical dependencies counted: include legal and operational prerequisites.
- Unconfirmed promise treated as available: label confidence.

## Handoffs

Architect evaluates coupling; Project Manager coordinates dates; relevant policy owner resolves approvals.
