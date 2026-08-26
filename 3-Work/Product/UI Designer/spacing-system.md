# Spacing System

Context: [UI Designer](README.md).

## Purpose

Define consistent spacing relationships for a coherent interface.

## Activate When

Spacing feels arbitrary or components need shared rhythm.

## Do Not Use When

Do not use spacing tokens to compensate for a broken layout or unclear hierarchy.

## Required Context

**Needed:** Repeated component/layout examples, density needs, and existing spacing values.

**Can be deferred or bounded:** A full design system is optional; start with a small scale grounded in actual relationships.

## Workflow

1. Measure existing repeated gaps and identify intentional versus accidental variation.
2. Choose a small scale appropriate to density and touch contexts.
3. Assign spacing by relationship: within controls, between related fields, and between sections.
4. Apply the rules to dense and sparse screens and record exceptions with reasons.

## Relationship Mapping

Group measured gaps by meaning: within a control, related fields, sections, and page regions. Consolidate near-duplicates only when meaning and readability remain intact. Specify density variants deliberately; a compact display should not unintentionally reduce target separation or collapse error-message space.

## Decision Rules

- If two gaps express the same relationship, prefer one token.
- If density impairs readability or target separation, increase space or change layout.

## Output Contract

Spacing scale, semantic usage rules, component mappings, and justified exceptions.

## Quality Gates

- Are tokens used consistently across comparable components?
- Do changes preserve hierarchy and usable target spacing?
- Comparable relationships use consistent spacing and exceptions have a content-based reason.

## Failure Modes

- Many near-identical tokens: consolidate meaningful roles.
- Rigid scale harms content: allow documented exceptions.

## Handoffs

UI [component-design.md](component-design.md) and [layout-design.md](layout-design.md) consume the spacing rules; Frontend Engineer maps tokens to code.
