# Timeline Design

Context: [Planner](README.md).

## Purpose

Schedule dependencies, estimates, buffers and decision lead times.

## When to Use

An accepted scope needs dependency-aware timing or a deadline feasibility assessment.

## Boundary

A deadline is not an estimate and critical path is not the only resource limit.

## Inputs

Outcome dependencies, effort/duration ranges, calendars, resource limits, waiting/approval lead times and deadline meaning.

## Method

1. Distinguish effort, elapsed duration and external waiting. Confirm start conditions and calendar versus working-time conventions before adding durations.
2. Build the dependency network and identify paths that determine finish timing. Check resource contention: tasks that look parallel may require the same scarce capability.
3. Use implementer estimates or bounded ranges, including acceptance, integration and rework. Keep target dates separate from evidence-backed forecasts.
4. Place buffers against identified uncertainty without counting the same allowance in every estimate and again at the end. Test correlated delays rather than adding incompatible percentile estimates.
5. Set latest-useful decision dates and checkpoints before irreversible dependencies. If the deadline is infeasible, show scope/sequence/resource choices and their supported consequences.

## Timing That Can Change a Decision

A checkpoint after the last feasible intervention is only reporting. Work backward from the consequence to reserve approval and response lead time. A critical path describes precedence under stated assumptions; a capacity bottleneck can impose a different binding limit. Unknown external dates remain conditional instead of becoming promises.

## Output

Timeline or dependency sequence, assumptions/ranges, binding path/resource, buffer rationale, decision dates and contingency choices.

## Quality Checks

- The same calendar and units are used throughout; waiting time is not counted as usable effort.
- No schedule is declared committed without the applicable owner and dependent parties accepting it.

## Handoffs

[Resource-planning](resource-planning.md) supplies capacity; [execution-review](execution-review.md) updates the forecast from real progress.
