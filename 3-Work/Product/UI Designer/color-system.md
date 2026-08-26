# Color System

Context: [UI Designer](README.md).

## Purpose

Define semantic color roles with accessible and consistent state communication.

## Activate When

Colors are inconsistent or state meaning relies on arbitrary hues.

## Do Not Use When

Do not claim accessibility from palette selection alone or change brand without approval.

## Required Context

**Needed:** Existing palette or explicit design mandate, semantic states, foreground/background uses, and target accessibility needs.

**Can be deferred or bounded:** Without a brand palette, propose a labeled provisional system; conformance needs rendered-state checks.

## Workflow

1. Inspect actual foreground/background pairs and existing status meanings.
2. Assign colors by semantic role, separating brand, action, feedback, and surfaces.
3. Check relevant contrast requirements in real states including disabled, focus, and selected variants.
4. Pair status color with text, icon, or structure and test theme and image-background cases.

## Color Pair Ledger

Record token role, foreground/background pair, theme, state, measured contrast, and non-color cue. Check error and focus colors against adjacent surfaces, not only against white. Distinguish accessibility requirements for active controls from applicable exceptions; do not claim every disabled control has the same contrast obligation.

## Decision Rules

- If a brand color fails a required contrast use, adjust its role or use an approved variant.
- If color is the only signal, add a second cue.

## Output Contract

Semantic tokens, contrast evidence, state mappings, theme behavior, and non-color cues.

## Quality Gates

- Are critical text and control pairs checked against the chosen accessibility target?
- Do themes preserve meaning and contrast?
- Status remains understandable in monochrome and contrast is measured on actual pairings.

## Failure Modes

- Palette swatches mistaken for UI contrast: test actual pairs.
- Red/green alone communicates status: add labels or symbols.

## Handoffs

Frontend Engineer verifies rendered contrast; UX Designer confirms status meaning; use current W3C guidance for specific criteria.
