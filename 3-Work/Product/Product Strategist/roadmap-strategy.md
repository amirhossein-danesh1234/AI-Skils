# Roadmap Strategy

Context: [Product Strategist](README.md).

## Purpose

Sequence outcome bets so learning and dependencies shape product investment.

## Activate When

A product direction needs a credible sequence of investment themes.

## Do Not Use When

Project Manager owns delivery commitments; [release-planning.md](../Product%20Manager/release-planning.md) owns a bounded release.

## Required Context

**Needed:** Accepted direction, outcome bets, evidence dependencies, and capacity envelope.

**Can be deferred or bounded:** Distant dates should remain horizons; only authorized delivery commitments get specific promised dates.

## Workflow

1. Inspect current commitments and compare each proposed theme with strategic choices.
2. Identify capability and evidence dependencies; prioritize learning that can invalidate later investment.
3. Group bets by outcome and confidence rather than presenting a feature wish list.
4. Sequence near-term committed work separately from contingent options and define review triggers.

## Learning Sequence

Place assumption-breaking tests before dependent implementation. Distinguish outcomes to learn, capabilities to enable, and releases already committed. If a delayed experiment invalidates later bets, show the branch in the roadmap instead of keeping a fixed feature sequence.

## Decision Rules

- If a later bet depends on an untested assumption, schedule validation before committing its implementation.
- If dates are externally committed, obtain delivery feasibility rather than estimating from strategic desirability.

## Output Contract

Outcome roadmap with horizon, confidence, dependencies, learning gates, and explicit non-commitments.

## Quality Gates

- Are time horizons and confidence clearly distinguished from promised dates?
- Does every theme have an outcome and a reason for its sequence?
- A failed early gate can change or remove later investment rather than merely shift dates.

## Failure Modes

- Roadmap as fixed contract: label conditional items and review triggers.
- All priorities simultaneous: expose capacity trade-offs.

## Handoffs

Product Manager scopes increments; Project Manager validates capacity and dependencies; Product Analyst defines outcome signals.
