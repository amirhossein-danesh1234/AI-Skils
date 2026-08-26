# Investment Analysis

Context: [Financial Analyst](README.md).

## Purpose

Compare an investment’s incremental future value with alternatives and downside.

## Activate When

A capital, project, or build-versus-buy decision requires economic analysis.

## Do Not Use When

Do not provide personal investment suitability advice or count sunk costs as future benefit.

## Required Context

**Needed:** Incremental alternatives, future cash drivers, horizon, funding limits, and risk.

**Can be deferred or bounded:** Unsupported discount/terminal assumptions require sensitivity or a simpler bounded comparison, not false precision.

## Workflow

1. Define the baseline including no investment and identify incremental benefits and costs.
2. Model timing, maintenance, working capital, residual value, and exit costs.
3. Use suitable discounted cash flow, payback, or other methods with stated limitations and consistent nominal/real assumptions.
4. Test downside, delay, adoption, and alternative uses of scarce capital.

## Incremental Value and Decision Sensitivity

Use a consistent baseline and include doing nothing, delaying, reducing scope, buying, leasing, or partnering where credible. Count future incremental cash consequences, including implementation, training, maintenance, working capital, disruption, and exit or residual value. Sunk costs may explain context but must not be treated as recoverable future benefits.

If discounted cash flow is appropriate, keep cash-flow timing and discount conventions consistent. Do not mix real cash flows with a nominal rate or different currencies without a justified conversion method. Explain discount-rate assumptions and avoid a terminal value that silently supplies most of the result without evidence.

Show break conditions for adoption, price, delay, cost, or useful life. Payback can expose liquidity timing but ignores value beyond the cutoff; NPV depends on uncertain cash flows and discounting. Use these measures as decision aids rather than automatic authority. Consider staged investment when learning can reduce irreversible exposure.

## Decision Boundary

Show the adoption, useful life, cost, or delay at which the preferred option changes. Separate payback timing from total value and include exit obligations. Route company-level attention/capital allocation to Founder Advisor; a favorable NPV alone does not authorize investment.

## Decision Rules

- If discount rate or terminal value dominates the result, expose sensitivity and seek justified assumptions.
- If benefits are unverified, stage commitment or run a proof before full investment.

## Output Contract

Investment comparison with cash flows, valuation method, assumptions, sensitivity, opportunity cost, and recommendation.

## Quality Gates

- Are cash flows incremental and double counting avoided?
- Does the recommendation fit financing and risk constraints?
- All alternatives use consistent scope, timing, currency, and incremental baseline.

## Failure Modes

- Sunk cost drives choice: compare future alternatives.
- Precise NPV hides weak inputs: show ranges.

## Handoffs

Business Strategist assesses strategic fit; engineers assess feasibility; qualified finance professionals and executive owner approve major commitments.
