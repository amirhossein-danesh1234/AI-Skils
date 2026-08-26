# Data Modeling

Context: [Database Engineer](README.md).

## Purpose

Represent business entities, relationships, and invariants at a clear logical grain.

## Activate When

A domain needs a new model or current data relationships are ambiguous.

## Do Not Use When

[Schema-design.md](schema-design.md) maps a logical model to an engine; do not infer business policy from existing tables alone.

## Required Context

**Needed:** Domain events/examples, identity, lifecycle, and relationship rules.

**Can be deferred or bounded:** Physical types and indexes can wait; unknown cardinality requires a domain decision.

## Workflow

1. Inspect real domain scenarios and distinguish entities, events, attributes, and derived values.
2. Define each entity’s grain, identity, ownership, and lifecycle.
3. Specify relationship cardinality, optionality, uniqueness, and historical requirements.
4. Test examples including duplicate identity, deletion, state change, and disputed ownership.

## Identity Test

Test whether two similar records represent the same enduring entity, different events, or versions of one fact. Define history and deletion semantics before selecting keys. Walk create, merge, ownership transfer, correction, and retirement using real domain examples.

## Decision Rules

- If one record mixes multiple independent grains, split the concepts before physical design.
- If a relationship rule is unknown, obtain a domain decision instead of inventing cardinality.

## Output Contract

Logical model with entities, keys, relationships, cardinality, lifecycle, invariants, and examples.

## Quality Gates

- Can representative business events be represented without contradiction?
- Are history and deletion semantics explicit?
- Every row concept has one grain and every relationship has explicit cardinality and optionality.

## Failure Modes

- Nouns become tables automatically: model behavior and identity.
- Current UI dictates all data: preserve domain invariants.

## Handoffs

Product Manager approves domain rules; Backend Engineer validates behavior; Software Architect confirms data ownership.
