# Market Sizing

Context: [Market Researcher](README.md).

## Purpose

Estimate a defined market with transparent assumptions and sensitivity.

## Activate When

A market opportunity needs a bounded economic scale estimate.

## Do Not Use When

Do not use a large TAM as evidence of reachable revenue or apply an arbitrary market-share percentage.

## Required Context

**Needed:** Customer/economic unit, geography, period, product boundary, and available sources.

**Can be deferred or bounded:** Without supported inputs, return formulas and defensible bounds; no invented base case or arbitrary market share.

## Workflow

1. Define the eligible customer and avoid overlapping categories.
2. Build a bottom-up estimate from customer counts, purchase frequency, units, and price or spend.
3. Constrain serviceable scope by product, geography, regulation, and channel access.
4. Estimate obtainable demand from sales capacity, conversion, delivery capacity, competition, and time; cross-check external totals.

## Sizing Model Contract

Choose one economic unit and period. A customer-count model might use eligible organizations × annual relevant spend per organization; a transaction model might use eligible buyers × purchases per year × units per purchase × realized unit price. Do not mix revenue, transaction value, user counts, and total industry spending as if interchangeable.

Define TAM as the full market matching the stated problem and scope, SAM as the portion serviceable under actual product, geography, distribution, and regulatory constraints, and SOM as a time-bounded obtainable outcome supported by acquisition and fulfillment capacity. Use these labels only when they clarify the decision.

Build the bottom-up model first when usable data exists. For every input, record source, period, geography, definition, evidence type, and range. De-duplicate overlapping customer groups. If a top-down report uses a broader category, explain the bridge rather than applying an unexplained percentage.

Constrain SOM with a realistic path: reachable accounts, qualification, conversion, sales-cycle timing, retention, available sales effort, and delivery capacity. Do not assume a small percentage of a large TAM is automatically attainable. Reconcile customer counts and spending units with independent totals where possible.

Show which assumptions dominate the estimate and how conclusions change across plausible values. Report a supported range and base case only when the evidence permits them. Otherwise return the formulas, defensible upper or lower bounds, and missing inputs; do not invent a midpoint or probability distribution. The recommendation must distinguish market size from market attractiveness, access, and economic viability.

## Obtainable Demand

Distinguish establishments from buying organizations and users from paying accounts. Build acquisition cohorts by sales-cycle timing and cap by onboarding/fulfillment capacity. A ceiling is not a forecast: show the unknown conversion or demand parameter that prevents a point estimate.

## Decision Rules

- If counts or price are uncertain, use explicit ranges and sensitivity rather than false precision.
- If top-down and bottom-up estimates diverge, reconcile definitions before averaging.

## Output Contract

TAM, SAM, and SOM definitions where useful; bottom-up model, top-down cross-check, ranges, sensitivities, and evidence quality.

## Quality Gates

- Are units, currency, dates, and customer counts consistent?
- Does SOM reflect a feasible acquisition and fulfillment path?
- TAM/SAM/SOM labels, if used, refer to consistent units and do not imply market attractiveness.

## Failure Modes

- Arbitrary share produces revenue: model capacity and conversion.
- Double-counted segments inflate totals: reconcile overlap.

## Handoffs

Financial Analyst checks formulas; Business Strategist assesses attractiveness; Sales validates acquisition capacity.
