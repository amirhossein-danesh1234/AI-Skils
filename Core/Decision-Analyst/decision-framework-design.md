# Decision Framework Design

Context: [Decision-Analyst](README.md).

## Purpose

Design criteria, vetoes and elicited weights before scoring options.

## When to Use

A repeated or contested choice needs explicit criteria and a defensible comparison method before options are scored.

## Boundary

A weighted score cannot override a hard constraint.

## Inputs

Decision scope, owner objectives, feasible attribute ranges, hard constraints and evidence quality.

## Method

1. Separate non-negotiable eligibility gates from preferences. State who owns each gate; do not let a high benefit score compensate for a prohibited action.
2. Choose criteria that distinguish outcomes relevant to the owner. Remove proxies that double-count the same benefit, and separate consequence from confidence in its estimate.
3. Define scale anchors and direction using meaningful best/worst feasible outcomes. Elicit trade-offs over those ranges; a weight on a tiny swing is not comparable to a weight on a large swing without calibration.
4. Select a method suited to the choice: constraint screen, dominance, explicit trade-off narrative or weighted model. Use weights only when compensatory trade-offs and the scale assumptions are defensible.
5. Test the framework on an edge case and vary weights/ranges. Record whether the ordering is stable and which preference clarification would change it.

## Scoring Discipline

Write down criteria before seeing the final score where practical. A weighted sum is a model of preferences, not an objective ranking machine. Correlated criteria can count the same benefit twice. If sensible weights yield different winners, present the disagreement and threshold rather than optimizing weights to match the favored option.

## Output

Criteria/gate definitions, scale anchors, elicited weights or qualitative rule, evidence treatment, sensitivity results and owner questions.

## Quality Checks

- A clearly inadmissible option cannot win through compensation.
- Uncertainty in evidence is visible separately from the owner’s valuation of the outcome.

## Handoffs

[Option-comparison](option-comparison.md) applies the framework; specialists validate domain gates and the actual owner confirms preferences.
