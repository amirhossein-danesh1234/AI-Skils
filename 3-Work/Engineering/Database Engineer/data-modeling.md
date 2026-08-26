# Data Modeling

## Purpose

Represent business entities, relationships, and invariants at a clear logical grain.

## When to Use

A domain needs a new model or current data relationships are ambiguous.

## When Not to Use

Schema-design.md maps a logical model to an engine; do not infer business policy from existing tables alone.

## Required Inputs

### Required

Business rules, representative records, lifecycle states, identity rules, and access needs.

### Helpful

Database engine/version, schema, constraints, workload evidence, volumes, retention needs, and recovery objectives.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Logical model with entities, keys, relationships, cardinality, lifecycle, invariants, and examples.

## Operating Principles

Design from invariants and access patterns; verify query semantics separately from speed and migration safety separately from syntax.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect real domain scenarios and distinguish entities, events, attributes, and derived values.
2. Define each entity’s grain, identity, ownership, and lifecycle.
3. Specify relationship cardinality, optionality, uniqueness, and historical requirements.
4. Test examples including duplicate identity, deletion, state change, and disputed ownership.

## Decision Rules

- If one record mixes multiple independent grains, split the concepts before physical design.
- If a relationship rule is unknown, obtain a domain decision instead of inventing cardinality.

## Validation

- Can representative business events be represented without contradiction?
- Are history and deletion semantics explicit?

## Common Failure Modes

- Nouns become tables automatically: model behavior and identity.
- Current UI dictates all data: preserve domain invariants.

## Escalation and Collaboration

Product Manager approves domain rules; Backend Engineer validates behavior; Software Architect confirms data ownership.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
