# Financial Forecasting

## Purpose

Build a driver-based forecast that separates history, assumptions, and uncertainty.

## When to Use

A business needs a forward view for planning or resource decisions.

## When Not to Use

Do not extend historical percentages mechanically or present forecast precision as certainty.

## Required Inputs

### Required

Historical records, operating drivers, planned changes, time horizon, currency, and financing constraints.

### Helpful

Decision scope, actual financial records, currency, period, accounting basis, business drivers, and financing constraints.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Forecast with assumptions, linked revenue/cost/cash drivers, scenarios, sensitivities, reconciliation, and update rules.

## Operating Principles

Keep historical data, forecast, assumption, scenario, and sensitivity distinct. Show units, timing, denominators, and downside exposure.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Reconcile historical baseline and identify seasonality, one-offs, and structural changes.
2. Choose drivers that explain the business rather than arbitrary growth rates.
3. Link revenue, costs, working capital, capital spending, and financing timing where relevant.
4. Construct coherent scenarios, check capacity and cash constraints, and compare past forecasts with actuals.

## Model Structure and Reconciliation

Keep historical actuals, assumptions, formulas, scenarios, and outputs distinguishable. Record source and as-of date for each material assumption. Use explicit units, currency, period, and sign conventions. Do not replace missing actuals with forecasts without labeling the substitution.

Build operating drivers such as customer count, conversion, retention, price, volume, staffing, utilization, and delivery cost only where they explain the business. Tie revenue to achievable activity and costs to the resources needed for that activity. Include seasonal and step changes when evidence supports them.

For cash, model collection and payment timing, inventory or work in progress, capital spending, debt movements, and restricted cash where relevant. Reconcile opening cash plus inflows minus outflows to closing cash each period. If a full balance-sheet forecast is in scope, check balance and consistency with profit and cash movements; do not fabricate a balancing plug without explanation.

Create coherent scenarios and one-way sensitivities separately. Inspect the first period of liquidity pressure and the operational action required before it arrives. Backtest prior forecasts against actuals to distinguish model bias from changed conditions. Forecasts should be updated when driver evidence changes, not only when a reporting date arrives.

The final output includes a recommendation, model limitations, dominant assumptions, downside consequences, and the next decision. Formal reporting treatment requires the applicable accounting policy and qualified review; [IAS 7](https://www.ifrs.org/issued-standards/list-of-standards/ias-7-statement-of-cash-flows/) is a reference for IFRS cash-flow reporting, not a universal policy for every organization.

## Decision Rules

- If a driver lacks evidence, label it and show the decision’s sensitivity to it.
- If the model implies impossible capacity or funding, revise assumptions rather than hide the gap.

## Validation

- Do balances and cash movements reconcile across periods?
- Are formulas, units, scenarios, and assumption sources traceable?

## Common Failure Modes

- Forecast copied from targets: separate ambition and expectation.
- Growth without working capital: model cash timing.

## Escalation and Collaboration

Operations and Sales validate drivers; accountant confirms reporting basis; executive owner approves planning assumptions.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
