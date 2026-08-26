# UI Designer — Component Design

Context: [UI Designer](README.md).

## Purpose

Specify reusable visual components with complete states and usage boundaries.

## Activate When

Repeated interface patterns need a consistent visual contract.

## Do Not Use When

Frontend Engineer owns component code architecture; UX Designer owns interaction policy.

## Required Context

**Needed:** Approved interaction, existing tokens/components, and real consumer variants.

**Can be deferred or bounded:** Implementation API can be refined with Frontend; behavior and essential states cannot be guessed from appearance.

## Workflow

1. Inspect existing patterns and decide whether a component already satisfies the need.
2. Define anatomy and semantic variants before cosmetic options.
3. Specify default, hover, focus, active, disabled, loading, error, empty, and selected states as applicable.
4. Test composition, long content, small viewports, and keyboard-visible state.

## Variant Contract

Separate semantic variants from sizes and states. For each meaningful combination, define anatomy, content constraints, visual tokens, focus/error/loading behavior, and forbidden combinations. Include a long localized label and no-data state to expose geometry assumptions before handoff.

## Decision Rules

- If variants express unrelated tasks, use separate components rather than one configuration-heavy control.
- If a new variant duplicates an existing semantic role, reuse it.

## Output Contract

Component anatomy, variants, states, sizing, content rules, and appropriate-use guidance.

## Quality Gates

- Can implementation distinguish every meaningful state without guessing?
- Are tokens and behavior consistent with the design system?
- Frontend can map variants to code without inventing interaction policy.

## Failure Modes

- Only default state designed: enumerate applicable states.
- Variant explosion: require a real use case for each variant.

## Handoffs

UX Designer approves behavior; Frontend Engineer maps the specification to accessible APIs.
