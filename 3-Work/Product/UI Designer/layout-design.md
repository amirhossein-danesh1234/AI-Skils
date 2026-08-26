# Layout Design

Context: [UI Designer](README.md).

## Purpose

Arrange approved content into stable, readable screen structures.

## Activate When

A page needs a layout or a layout fails under realistic content.

## Do Not Use When

Responsive behavior across widths belongs with [responsive-design.md](responsive-design.md); do not redefine navigation strategy.

## Required Context

**Needed:** Approved content/task order and target layout constraints.

**Can be deferred or bounded:** Exact breakpoints may follow content stress tests; the logical reading order is required.

## Workflow

1. Inspect reading order, task sequence, and existing layout conventions.
2. Group related content and select a grid that supports primary and secondary regions.
3. Define width constraints, alignment, wrapping, and overflow instead of relying on fixed mockup dimensions.
4. Test dense, empty, long-text, translated, and permission-reduced content.

## Content Stress Layout

Use realistic empty, dense, long translated, and restricted-permission variants. Specify minimum/maximum widths, wrapping, intrinsic height, alignment, and overflow. Distinguish deliberate scroll regions from accidental clipping; avoid fixed heights for variable text unless an accessible expansion behavior is defined.

## Decision Rules

- If a layout needs arbitrary offsets for ordinary content, revise the structure.
- If columns make reading or input cramped, change composition rather than shrinking text.

## Output Contract

Layout specification with grid, regions, alignment, sizing, overflow, and content stress cases.

## Quality Gates

- Does reading and focus order match visual order?
- Can realistic content fit without overlap or hidden actions?
- The layout preserves content and primary actions under each relevant stress case.

## Failure Modes

- Perfect sample content hides overflow: stress-test real extremes.
- Fixed heights clip text: define flexible sizing.

## Handoffs

UX Designer approves grouping and task sequence; Frontend Engineer checks feasible layout rules.
