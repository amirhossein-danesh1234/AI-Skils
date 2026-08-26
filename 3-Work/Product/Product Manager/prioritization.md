# Prioritization

Context: [Product Manager](README.md).

## Purpose

Order product work by expected value, risk, learning, and cost under real constraints.

## Activate When

A backlog exceeds capacity or competing requests need an explicit decision.

## Do Not Use When

[Product strategic-prioritization](../Product%20Strategist/strategic-prioritization.md) chooses product bets; Project Manager sequences delivery dependencies after value choices.

## Required Context

**Needed:** Candidate work, value evidence, obligations, and capacity constraints.

**Can be deferred or bounded:** Effort may be an implementer range; unsupported reach or confidence must not become a precise score.

## Workflow

1. Inspect whether each item addresses a supported problem and remove duplicates.
2. Separate mandatory obligations and blocking dependencies from discretionary value choices.
3. Compare impact, reach, confidence, effort, risk reduction, learning, and cost of delay using available evidence.
4. Test sensitivity and select a feasible set, including no-build alternatives.

## Comparable Choice Set

Normalize candidates to similar decision size and combine prerequisite bundles. Separate urgent remediation from elective value and identify the marginal item excluded by capacity. Show what evidence or estimate change would swap the top two choices; if none can, a complex scoring framework is unnecessary.

## Decision Rules

- If uncertain inputs dominate a score, use ranges or a discovery task instead of false precision.
- If a low-value item unlocks a high-value outcome, evaluate the dependency bundle.

## Output Contract

Ordered backlog or priority tiers with rationale, deferred work, uncertainty, and revisit conditions.

## Quality Gates

- Does the choice fit capacity and identify what is displaced?
- Are stakeholder urgency and evidence of value distinguished?
- The selected set fits the actual bottleneck resource, not only a nominal total effort.

## Failure Modes

- Highest score treated as automatic truth: explain judgment.
- Everything high priority: force a bounded selection.

## Handoffs

Product Strategist validates direction; engineers validate effort; Project Manager checks feasible sequencing.
