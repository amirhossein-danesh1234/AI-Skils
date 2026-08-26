# Break Even Analysis

Context: [Financial Analyst](README.md).

## Purpose

Estimate the activity level at which defined revenues cover defined costs.

## Activate When

A product, project, or operating change needs a viability threshold.

## Do Not Use When

Do not use a single linear break-even point when costs or prices change materially with volume.

## Required Context

**Needed:** Defined revenue/cost scope, unit or mix, period, and feasible capacity.

**Can be deferred or bounded:** Without supported inputs, give equations and break conditions; do not invent demand or a precise threshold.

## Workflow

1. Define the decision scope and distinguish avoidable from sunk costs.
2. Calculate contribution per unit or weighted contribution for a justified mix.
3. Solve the threshold and inspect step costs, discounts, capacity, and working-capital needs.
4. Test plausible price, cost, and mix changes and compare with achievable demand.

## Threshold Interpretation

For a linear single-unit model, contribution=price-variable cost and operating break-even=fixed cost/contribution. State the applicable range and change the model for step costs or mix. Distinguish customers acquired late in a year from full customer-years of revenue; timing can invalidate a simple annual threshold.

## Decision Rules

- If contribution is nonpositive, volume alone cannot produce break-even under the model.
- If the threshold exceeds capacity or demand, recommend redesign or rejection rather than optimistic scaling.

## Output Contract

Break-even model with contribution assumptions, threshold range, capacity check, sensitivity, and limitations.

## Quality Gates

- Are cost classifications and formulas consistent?
- Does the model include discontinuities and feasible operating range?
- Achievability is tested against supported capacity and demand over a named horizon; an infeasible threshold supports a completed redesign/rejection recommendation. Keep cash sufficiency distinct.

## Failure Modes

- Fixed cost assumed constant at all scale: model steps.
- Accounting break-even mistaken for cash sufficiency: check timing.

## Handoffs

Operations confirms capacity; Market Researcher tests demand; Business Strategist evaluates alternatives.
