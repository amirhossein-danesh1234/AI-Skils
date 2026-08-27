# transportation-planning

[Travel Planner](README.md) / [Leisure domain](../../README.md)

## Travel Goal

Compare travel legs by door-to-door time, cost, reliability and disruption exposure.

## Use This For

Travel legs need comparison and connection design.

## Travel Boundary

Does not treat scheduled departure time as total journey time or guarantee operations.

## Trip Context

Origins/destinations, dates/local times, party/access/luggage, budget, flexibility, arrival constraints, passports/transit requirements if relevant and disruption tolerance.

## Travel Workflow

1. Define door-to-door endpoints and required arrival window, including first/last-mile and transfer constraints.
2. Research current schedules/fares/conditions from operators and official sources, including baggage, changes/refunds, check-in/security, border/transit and accessibility.
3. Compare options on total journey time, all-in cost, connection robustness, fatigue, overnight effects and failure recovery—not headline duration alone.
4. Recommend a route with buffers and backup/rebooking logic; list facts to verify immediately before purchase and travel.

## Connection Risk

Evaluate minimum connection rules, separate tickets, terminal/station changes, immigration/baggage recheck, last services and consequence of delay. A technically valid connection may be fragile.

## Travel Decision Rules

- Schedules, fares, strikes, regulations and operator policies are volatile.
- Do not recommend purchasing or hold traveler data without authority.

## Travel Output

Route plan with door-to-door timeline, fare/terms, luggage/access, connection analysis, buffers, fallback and verification/booking checklist.

## Feasibility and Currency Gates

- All local times, time zones and connection steps reconcile.
- The fallback is actionable if a material leg fails.

## Travel Failure Modes

- **Cheapest fare hides separate-ticket risk:** expose.
- **Flight/train duration substitutes for journey time:** include ends.

## Handoffs

Itinerary integrates; Budget totals; Risk Review checks disruption/advisories; official authorities handle transit entry rules.
