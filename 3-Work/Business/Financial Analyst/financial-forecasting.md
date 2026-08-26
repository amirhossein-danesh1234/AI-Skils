# Financial Forecasting

Context: [Financial Analyst](README.md).

## Purpose

Build a driver-based forecast that separates history, assumptions, and uncertainty.

## Activate When

A business needs a forward view for planning or resource decisions.

## Do Not Use When

Do not extend historical percentages mechanically or present forecast precision as certainty.

## Required Context

**Needed:** Historical baseline or explicit pre-revenue status, operating drivers, horizon, and constraints.

**Can be deferred or bounded:** A new business may use assumptions only, labeled clearly; no invented historical records or unsupported base case.

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

## Forecast Accountability

Link each driver to an operational owner and evidence update trigger. Reconcile growth with sales cycle, onboarding, staffing, and working capital. Backtest forecasts against actuals by driver to separate biased assumptions from changed conditions, then revise forward expectations without rewriting history.

## Decision Rules

- If a driver lacks evidence, label it and show the decision’s sensitivity to it.
- If the model implies impossible capacity or funding, revise assumptions rather than hide the gap.

## Output Contract

Forecast with assumptions, linked revenue/cost/cash drivers, scenarios, sensitivities, reconciliation, and update rules.

## Quality Gates

- Do balances and cash movements reconcile across periods?
- Are formulas, units, scenarios, and assumption sources traceable?
- A target is not presented as the expected outcome unless the driver evidence supports it.

## Failure Modes

- Forecast copied from targets: separate ambition and expectation.
- Growth without working capital: model cash timing.

## Handoffs

Operations and Sales validate drivers; accountant confirms reporting basis; executive owner approves planning assumptions.
