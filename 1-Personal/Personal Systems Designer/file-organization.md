# file-organization

[Personal Systems Designer](README.md) / [Personal domain](../../README.md)

## Purpose

Create discoverable personal file rules with reversible migration and archive boundaries.

## Activate When

Personal digital artifacts are hard to retrieve, duplicated or inconsistently stored.

## Do Not Use When

No deletion, renaming or broad migration without explicit scope.

## Required Context

**Needed**

Artifact types, retrieval situations, existing locations, sharing/sensitivity, retention needs, platform constraints and failure examples.

**Can be deferred or bounded**

Bulk migration and detailed naming exceptions may wait for a pilot.

## Workflow

1. Sample actual retrieval failures and identify the primary retrieval cues: project, person, date, type or status.
2. Choose a shallow home model, minimal naming convention and separation for active, reference, archive and sensitive material. Avoid duplicating source-of-truth files.
3. Define capture, move/archive, duplicate resolution, backup and access rules. Pilot with one representative area before migrating.
4. Test retrieval with realistic queries and measure time/misfiles; document exceptions and a reversible migration plan.

## Retrieval Before Taxonomy

Organization succeeds when the owner can save and retrieve reliably, not when every item fits an elaborate ontology. Search, metadata and folders can coexist, but each rule must solve an observed failure.

## Decision Rules

- Keep sensitive records in appropriately protected locations with least necessary access.
- Do not mass rename, move or delete without exact scope, backup/rollback and authorization.

## Output Contract

File system guide with source-of-truth locations, shallow structure, naming examples, capture/archive rules, privacy controls, migration and retrieval test.

## Quality Gates

- A new item has one obvious default location.
- The design reduces duplicate authority and does not depend on perfect filing.

## Failure Modes

- **Taxonomy mirrors abstract life categories but not retrieval behavior:** redesign around use.
- **Migration becomes a cleanup project without payoff:** pilot and bound it.

## Handoffs

PKM organizes knowledge derived from artifacts; Automation may assist only after conventions stabilize; backup/security specialists handle high-risk storage.
