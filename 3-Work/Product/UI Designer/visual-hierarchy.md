# Visual Hierarchy

Context: [UI Designer](README.md).

## Purpose

Make the most important information and action visually apparent.

## Activate When

Users miss priorities or a screen competes for attention.

## Do Not Use When

Do not change task order or product priorities without UX and Product Manager agreement.

## Required Context

**Needed:** Primary task, approved content importance, and screen context.

**Can be deferred or bounded:** Decoration and new brand choices can wait; priority cannot be inferred from stakeholder enthusiasm.

## Workflow

1. Inspect what the user must notice, understand, and act on in sequence.
2. Rank content by task importance, not stakeholder preference.
3. Use position, spacing, size, weight, and contrast coherently; avoid relying only on color.
4. Check the screen at small size, with long content, and without decorative imagery.

## Attention Walk

Identify what the user must notice first, understand next, and act on. Use size, placement, spacing, and contrast coherently; test without imagery and color. A warning or completion state must remain recognizable even when promotional content competes for attention.

## Decision Rules

- If several actions look primary, choose one per meaningful decision context.
- If emphasis obscures essential warnings or status, rebalance it.

## Output Contract

Hierarchy specification with emphasis levels, grouping, primary action, and rationale.

## Quality Gates

- Can a viewer identify the primary task and current state quickly?
- Does emphasis remain understandable without color alone?
- A viewer can identify the primary action and current state without explanatory narration.

## Failure Modes

- Everything bold: create differentiated levels.
- Promotional content outranks task needs: restore functional priority.

## Handoffs

UX Designer confirms task importance; Frontend Engineer verifies rendered hierarchy.
