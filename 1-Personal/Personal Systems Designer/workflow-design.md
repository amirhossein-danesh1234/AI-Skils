# workflow-design

[Personal Systems Designer](README.md) / [Personal domain](../../README.md)

## Purpose

Design the minimal reliable sequence for a recurring personal outcome.

## Activate When

A recurring personal outcome crosses several steps or tools and suffers delay, ambiguity, rework or handoff loss.

## Do Not Use When

Not software architecture or ceremony for a one-step routine.

## Required Context

**Needed**

Desired outcome/start/end, current steps, triggers, actors/tools, inputs/outputs, exceptions, frequency, pain points and constraints.

**Can be deferred or bounded**

Automation and new tooling are deferred until the manual flow is coherent.

## Workflow

1. Define trigger, done state and scope, then map the current path including wait states, rework, decisions and exceptions.
2. Find the material bottleneck or ambiguity using actual examples. Remove, combine or clarify steps before adding controls.
3. Design the smallest future-state sequence with explicit inputs, outputs, decision rules, ownership and exception path.
4. Pilot manually, measure completion time/errors/rework and revise. Document the stable flow and only then assess automation.

## Outcome-to-Outcome Flow

Optimize the whole outcome rather than making one step locally fast while moving burden downstream. A checklist may outperform a new application. Occasional workflows need less machinery than daily ones.

## Decision Rules

- Every step must transform, decide, verify or communicate something necessary.
- Exceptions have a safe holding state instead of silently falling through.

## Output Contract

Workflow specification with trigger/done, current issue, future steps, roles/tools, decision/exception rules, measures, pilot and review.

## Quality Gates

- The future flow directly addresses observed failure.
- Maintenance and adoption cost are proportionate to frequency and consequence.

## Failure Modes

- **Diagram detail hides unclear outcome:** restate start/done.
- **Automation chosen before simplification:** keep manual pilot.

## Handoffs

Task System handles commitments; File/PKM handle artifacts/knowledge; Automation and AI Workflow assess implementation modes.
