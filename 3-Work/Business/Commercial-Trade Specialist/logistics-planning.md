# Logistics Planning

Context: [Commercial-Trade Specialist](README.md).

## Purpose

Plan goods movement with realistic timing, responsibilities, and exception handling.

## Activate When

A shipment or recurring route needs a feasible logistics plan.

## Do Not Use When

Do not guarantee transit or customs clearance from a carrier estimate alone.

## Required Context

**Needed:** Goods/handling needs, origin/destination, quantities, delivery terms, and deadline basis.

**Can be deferred or bounded:** Carrier estimates are not guarantees; specialist handling or clearance needs confirmation before booking.

## Workflow

1. Inspect packaging, handling, hazardous or controlled classifications, and route constraints.
2. Compare modes and routes on total cost, transit variability, capacity, and damage exposure.
3. Assign pickup, handoff, clearance, delivery, and exception responsibilities.
4. Plan documentation lead times, buffers, tracking, and alternatives for disruption.

## End-to-End Time

Include manufacturing readiness, packaging, pickup, consolidation, main transit, clearance, final delivery, and waiting buffers. Name the owner and required document for each handoff. Compare an expedited contingency with the business cost of delay rather than selecting the cheapest route automatically.

## Decision Rules

- If a delay threatens a critical deadline, compare expedited cost with the business consequence.
- If goods require specialist handling or clearance, obtain qualified confirmation before booking.

## Output Contract

Route and mode plan with milestones, cost range, owners, documents, tracking, buffers, and contingencies.

## Quality Gates

- Are every handoff and document owner identified?
- Do timing and cost estimates include foreseeable waiting and clearance?
- A critical deadline is assessed against the entire route and variability, not carrier transit alone.

## Failure Modes

- Transit time excludes preparation: model end to end.
- Cheapest route ignores damage risk: include expected consequences.

## Handoffs

Operations manages execution; supplier and carrier confirm capacity; Commercial pricing includes total cost.
