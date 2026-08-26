# Responsive Implementation

Context: [Frontend Engineer](README.md).

## Purpose

Implement adaptive layouts that preserve functionality across supported conditions.

## Activate When

Approved responsive rules need code or a layout breaks at particular sizes.

## Do Not Use When

Do not invent missing mobile behavior or remove functionality to fit a screenshot.

## Required Context

**Needed:** Approved adaptation intent, supported conditions, and existing layout code.

**Can be deferred or bounded:** Unspecified mobile behavior needs a design decision; dimensions can be derived from content constraints.

## Workflow

1. Inspect current layout primitives and identify content-driven breakpoints.
2. Implement flexible sizing, reflow, overflow, and navigation using existing conventions.
3. Test narrow, wide, intermediate, zoomed, and long-content states with real interaction.
4. Check reading order, focus visibility, touch controls, and orientation before finalizing.

## Viewport Sweep

Check below, at, and above breakpoints, plus long content and zoom. Inspect overlays, sticky elements, focus visibility, safe overflow, and input behavior rather than screenshots alone. Keep DOM order consistent with reading and focus; avoid visually rearranging controls into a misleading sequence.

## Decision Rules

- If a required action is hidden at a breakpoint, provide an equivalent accessible route.
- If fixed dimensions cause clipping, fix layout constraints rather than shrinking content arbitrarily.

## Output Contract

Responsive implementation with documented adaptations and verified viewport/content states.

## Quality Gates

- Can the primary task finish at every supported size?
- Are horizontal overflow, overlays, keyboard access, and text zoom checked?
- Required actions remain reachable at narrow and intermediate widths.

## Failure Modes

- Only two screenshots tested: inspect intermediate widths.
- CSS visual order differs from focus order: align the structure.

## Handoffs

UI Designer resolves visual adaptation; UX Designer approves interaction changes; QA validates device coverage.
