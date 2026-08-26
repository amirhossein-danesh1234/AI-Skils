# Product Manager — Scope Management

Context: [Product Manager](README.md).

## Purpose

Protect a coherent product outcome while making additions and exclusions explicit.

## Activate When

A feature expands, requirements conflict, or an MVP needs a defensible boundary.

## Do Not Use When

Project Manager manages delivery baseline changes; this skill decides product inclusion and value.

## Required Context

**Needed:** Product goal, current in/out scenarios, and proposed changes.

**Can be deferred or bounded:** Detailed schedule impact can follow a product-value decision, but changes remain conditional until delivery feasibility is confirmed.

## Workflow

1. Inspect the smallest complete user outcome and existing commitments.
2. Classify additions as essential behavior, risk control, enhancement, or unrelated request.
3. Estimate the value, dependencies, maintenance, and opportunity cost of each addition.
4. Negotiate a coherent cut and update requirement and acceptance references.

## Coherent Cuts

Evaluate cuts at scenario boundaries. Removing a whole optional workflow may be safe; removing authorization or recovery from a retained workflow is not. For each addition, specify displaced scope or a separate future decision rather than hiding it under the MVP label.

## Decision Rules

- If a cut breaks safety, integrity, or the core outcome, cut a whole scenario instead.
- If a change is valuable but not necessary now, defer it with a revisit condition.

## Output Contract

In/out scope decision, affected scenarios, deferred alternatives, acceptance changes, and rationale.

## Quality Gates

- Can users complete the retained scenario without hidden manual gaps?
- Do exclusions, acceptance, and release communication agree?
- Retained users can complete a valid outcome with its essential integrity and safety controls.

## Failure Modes

- MVP means unsafe incomplete behavior: preserve essential controls.
- Quiet scope drift: record the decision and displaced work.

## Handoffs

Project Manager updates delivery impacts; UX and engineering assess coherent cuts; decision owner approves trade-offs.
