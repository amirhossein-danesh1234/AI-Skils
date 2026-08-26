# UI Review

Context: [UI Designer](README.md).

## Purpose

Find visual implementation differences and consistency defects against an approved design.

## Activate When

A mockup or rendered interface needs visual quality review.

## Do Not Use When

UX audit assesses task usability; code review assesses implementation correctness.

## Required Context

**Needed:** Approved reference, actual rendering, viewport/state, and accepted deviations.

**Can be deferred or bounded:** If only mockups are available, label the review design-only; a build result cannot substitute for rendering.

## Workflow

1. Inspect typography, spacing, alignment, hierarchy, color, and component states against the reference.
2. Compare multiple viewport and realistic content states, including loading and error.
3. Separate intentional adaptation from accidental mismatch.
4. Prioritize defects by readability, consistency, and task impact; retest corrected areas.

## Difference Triage

Record expected versus actual tokens, geometry, or state with a reproducible location. Separate approved responsive adaptation from accidental drift. Group repeated component defects by shared cause and re-inspect the corrected component in multiple consumers rather than counting each instance as a separate root problem.

## Decision Rules

- If a difference improves constraints but changes behavior, request UX review before accepting it.
- If reference and design system conflict, resolve the source of truth rather than patching locally.

## Output Contract

Prioritized visual findings with location, expected/actual behavior, evidence, and correction scope.

## Quality Gates

- Are findings reproducible at specified viewport and state?
- Have corrected screens been visually reinspected rather than only rebuilt?
- Each defect is a demonstrated mismatch or readability issue, not ungrounded personal taste.

## Failure Modes

- Pixel perfection ignores usability: prioritize meaningful differences.
- Build passes treated as visual proof: inspect rendered output.

## Handoffs

Frontend Engineer implements fixes; UX Designer resolves behavior changes; Product Manager approves scope changes.
