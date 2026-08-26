# Cash Flow Analysis

Context: [Financial Analyst](README.md).

## Purpose

Explain cash movement and identify liquidity pressure over a defined period.

## Activate When

A business needs to reconcile cash or assess near-term payment capacity.

## Do Not Use When

Profitability is not cash flow; do not provide formal accounting signoff.

## Required Context

**Needed:** Opening/closing cash, dated receipts/payments, currency, restrictions, and scope.

**Can be deferred or bounded:** Incomplete records require a reconciliation gap; do not fabricate a balancing item.

## Workflow

1. Reconcile opening cash plus inflows minus outflows to closing cash.
2. Separate operational, investment, and financing movements according to the applicable reporting basis.
3. Inspect receivables, payables, inventory, debt, and one-off timing effects.
4. Project material near-term obligations and test delayed receipts or unexpected outflows.

## Liquidity Bridge

Reconcile opening plus receipts minus payments, treating internal transfers consistently. Separate restricted funds, operating cash, and financing not yet committed. Inspect receivable collection dates and essential obligations; a profitable month may still contain a cash shortfall before receipts arrive.

## Decision Rules

- If balances do not reconcile, resolve or explicitly bound the gap before conclusions.
- If cash is restricted or unavailable, do not count it as free operating liquidity.

## Output Contract

Cash bridge with reconciled movements, timing drivers, shortfalls, scenarios, and actions.

## Quality Gates

- Are periods, currencies, signs, and transfers consistent?
- Are historical movements distinct from forecast assumptions?
- The conclusion uses actually available liquidity and identifies the first cash-pressure period.

## Failure Modes

- Profit used as available cash: reconcile timing.
- Internal transfers double-counted: consolidate carefully.

## Handoffs

Accountant confirms reporting treatment; Commercial specialist supplies payment terms; executive owner decides financing or spending.
