# Design System

Context: [UI Designer](README.md).

## Purpose

Create a maintainable contract connecting visual rules, components, and usage.

## Activate When

Multiple screens or teams need consistent design decisions.

## Do Not Use When

Do not build a large component catalog without demonstrated reuse or replace product discovery.

## Required Context

**Needed:** Used UI patterns, actual code components, design rules, and maintainers.

**Can be deferred or bounded:** A small team may start with tokens and a few used components; a complete catalog is not a prerequisite.

## Workflow

1. Audit repeated patterns and identify the inconsistencies with real maintenance or usability cost.
2. Define a minimal token and component foundation with clear semantic roles.
3. Specify states, accessibility expectations, composition, and exceptions for adopted components.
4. Assign ownership, contribution rules, compatibility expectations, and incremental migration.

## Adoption Boundary

Choose a limited foundation with a real consuming screen and a maintainer. Map design names to code names, stable semantic roles, version compatibility, and migration cost. Allow documented local exceptions when standardization would distort a unique task; review repetition before promoting a pattern.

## Decision Rules

- If a pattern has no repeated need, leave it local until evidence justifies standardization.
- If adoption cost exceeds current benefit, deliver a smaller foundation first.

## Output Contract

System scope, tokens, component inventory, usage rules, ownership, versioning, and adoption plan.

## Quality Gates

- Do design and code names and states map clearly?
- Can a contributor decide reuse versus extension and understand migration impact?
- At least one real screen can adopt the system without parallel conflicting tokens.

## Failure Modes

- Catalog without governance: assign maintenance responsibility.
- Abstract completeness over adoption: prioritize used patterns.

## Handoffs

Frontend Engineer owns implementation contracts; UX Designer validates interaction consistency; Product Manager negotiates migration scope.
