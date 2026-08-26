# User Story Design

Context: [Product Manager](README.md).

## Purpose

Express a useful slice of user value with enough context for refinement.

## Activate When

A capability needs user-centered slices for discussion and delivery.

## Do Not Use When

Stories are not a substitute for complex business rules, contracts, or a complete PRD.

## Required Context

**Needed:** Actor, intended outcome, scenario, and relevant rules.

**Can be deferred or bounded:** A story can reference shared rules instead of duplicating a PRD; uncertain feasibility is a separate discovery item.

## Workflow

1. Inspect the end-to-end scenario and identify independently useful outcomes.
2. Write the actor’s need and reason using the user’s language rather than technical layers.
3. Attach concrete examples and essential rule references without hiding complexity in a sentence.
4. Split by coherent behavior or risk, preserving a usable vertical outcome.

## Vertical Slice Test

Demonstrate the value of a slice from trigger through persisted outcome and feedback. Split by actor, rule variation, or supported scenario when each remains coherent; do not split only into database/backend/frontend tickets and call each a user story. Technical enabling work can be named honestly as a dependency.

## Decision Rules

- If a slice produces no observable user or operational value, reconsider a technical-layer split.
- If several actors have conflicting needs, create distinct scenarios rather than a universal user.

## Output Contract

Stories with value, context, acceptance, exclusions, and slicing rationale.

## Quality Gates

- Can each story be demonstrated and accepted?
- Do stories together cover the intended scenario without duplicated scope?
- The story can be demonstrated with concrete acceptance examples and an explicit exclusion.

## Failure Modes

- Formulaic sentence with no context: add real examples.
- Tiny fragments inflate backlog: preserve a meaningful outcome.

## Handoffs

UX Designer confirms task coherence; engineers assess slicing; QA checks acceptance.
