# Typography

Context: [UI Designer](README.md).

## Purpose

Define readable text roles and behavior across real content.

## Activate When

A product needs type roles or text is inconsistent or difficult to read.

## Do Not Use When

Do not invent brand identity or substitute typography for content clarity.

## Required Context

**Needed:** Text roles, languages, actual content, and available font constraints.

**Can be deferred or bounded:** Brand font decisions can be provisional; license and glyph support need verification before shipping.

## Workflow

1. Inspect available fonts, licensing constraints, glyph coverage, and actual content lengths.
2. Assign roles for headings, body, labels, controls, and data rather than styling each screen independently.
3. Set readable size, line height, measure, and contrast in the intended context.
4. Test zoom, long labels, numbers, mixed scripts, and fallback fonts.

## Text Stress Spec

Define role, family/fallback, weight, size, line height, measure, and wrapping. Check numbers, mixed scripts, long labels, user zoom, and font-loading fallback. Preserve hierarchy under fallback fonts; essential content needs wrapping or expansion instead of unexplained ellipsis.

## Decision Rules

- If a font lacks required glyphs or a usable license, choose an approved fallback.
- If text must be shrunk to fit, revisit layout or wording first.

## Output Contract

Type scale and role mapping with weight, line height, wrapping, fallback, and language checks.

## Quality Gates

- Are hierarchy and legibility preserved at supported sizes and zoom?
- Do mixed-language and numeric strings align and wrap sensibly?
- A supported-language sample stays readable with the real loaded and fallback fonts.

## Failure Modes

- Mockup-only font fails in production: verify availability.
- Truncation hides essential meaning: define expansion or wrapping.

## Handoffs

Frontend Engineer validates font loading and rendering; Product Manager approves material copy changes.
