# itinerary-planning

[Travel Planner](README.md) / [Leisure domain](../../README.md)

## Travel Goal

Sequence a realistic trip with transit, check-in/out, meals, rest, buffers and contingencies.

## Use This For

Confirmed or candidate trip components need a realistic day-by-day sequence.

## Travel Boundary

Distinguishes researched possibilities from booked commitments.

## Trip Context

Dates/time zones, arrival/departure, lodging/check-in/out, transport, selected activities, meal/rest/access needs, companions, booking status, luggage, weather and desired pace.

## Travel Workflow

1. Place immutable booked components first and label researched, tentative and booked status separately; normalize local times/time zones.
2. Build door-to-door legs with transfer, station/airport process, check-in/out, luggage and realistic buffers.
3. Group activities geographically and add meals, rest, queues and unstructured time; verify opening/transport facts near execution.
4. Create day-level and trip-level contingencies for delay, closure, weather, low energy and missed connection, with drop order and contact/booking notes.

## Day Feasibility Test

For each day reconcile start/end location, all transit, operating windows, reservation times, meals, rest and buffer. An activity’s advertised duration is not its itinerary footprint.

## Travel Decision Rules

- Do not use every available hour or schedule immediate activity after uncertain arrival.
- Packing/preparation should follow weather, activities, transport and restrictions—not a generic list.

## Travel Output

Itinerary with statuses, local times, door-to-door legs, check-in/out, meals/rest, buffers, booking/verification tasks, packing implications and contingencies.

## Feasibility and Currency Gates

- Every day is spatially and temporally feasible.
- The trip survives one likely disruption without losing all priority experiences.

## Travel Failure Modes

- **Transit omitted between pins:** calculate.
- **Booked and suggested items look identical:** label authority.

## Handoffs

Transportation supplies legs; Activity/Accommodation provide components; Risk Review supplies contingencies; Personal Planner only handles pre-trip life calendar.
