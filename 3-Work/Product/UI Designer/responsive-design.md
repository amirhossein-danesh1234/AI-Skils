# Responsive Design

Context: [UI Designer](README.md).

## Purpose

Specify how visual composition adapts to content and available space.

## Activate When

A design must work across viewport sizes and input contexts.

## Do Not Use When

Frontend [responsive-implementation.md](../../Engineering/Frontend%20Engineer/responsive-implementation.md) handles code; do not merely shrink a desktop mockup.

## Required Context

**Needed:** Same task/content across supported widths and input contexts.

**Can be deferred or bounded:** Device-specific pixel values can be derived later; document adaptation rules between reference screens.

## Workflow

1. Inspect minimum usable widths and content-driven breakpoints.
2. Decide what reflows, stacks, scrolls, or changes navigation while preserving task access.
3. Specify behavior between reference widths, not only at two screenshots.
4. Stress-test long text, zoom, keyboard focus, orientation, and touch interaction.

## Adaptation Decisions

For each region, choose reflow, stack, resize, scroll, or alternate navigation and explain what stays available. Test narrow zoomed content, landscape, overlays, and keyboard focus. A layout that hides a required action needs an equivalent path, not an assumption that mobile users do not need it.

## Decision Rules

- If hiding content removes required information or action, provide an equivalent accessible path.
- If a table cannot reflow without losing comparison, specify deliberate accessible horizontal navigation.

## Output Contract

Responsive rules for reflow, navigation, density, sizing, overflow, and state variants.

## Quality Gates

- Can the same primary task finish on each supported layout?
- Are intermediate widths and content extremes covered?
- Task completion and logical order survive intermediate widths, not only reference screenshots.

## Failure Modes

- Device labels replace rules: define content constraints.
- Desktop order copied blindly: preserve logical reading and focus order.

## Handoffs

UX Designer approves interaction changes; Frontend Engineer verifies actual breakpoints and overflow.
