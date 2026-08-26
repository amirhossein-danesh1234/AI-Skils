# Milestone Planning

Context: [Project Manager](README.md).

## Purpose

Define evidence-based checkpoints for meaningful delivery outcomes.

## Activate When

A project needs progress gates or external commitment checkpoints.

## Do Not Use When

Do not label activity completion or calendar dates as outcomes without acceptance evidence.

## Required Context

**Needed:** Outcome, decision gates, dependencies, acceptance owner, and forecast range.

**Can be deferred or bounded:** Dates may remain conditional until capacity/dependencies are confirmed; milestones need observable meaning first.

## Workflow

1. Inspect the project’s major uncertainty and dependency transitions.
2. Choose checkpoints that prove readiness or unlock a meaningful next stage.
3. Define acceptance evidence and required decision owners.
4. Sequence milestones with realistic lead time and contingency.

## Gate Design

Choose milestones that retire uncertainty or unlock a genuine next step. Include the evidence required and who decides whether to proceed. Avoid activity milestones such as coding complete when integration or acceptance is the actual gate; keep buffers visible between uncertain dependencies.

## Decision Rules

- If a milestone cannot be verified independently, rewrite it as an observable outcome.
- If a date is conditional on an external dependency, state the condition prominently.

## Output Contract

Milestone plan with outcome, evidence, owner, prerequisites, date confidence, and decision at the gate.

## Quality Gates

- Does each milestone support a decision or handoff?
- Are prerequisites and acceptance owners clear?
- A milestone can fail honestly and trigger a specific change rather than only update a status color.

## Failure Modes

- Percent complete substitutes for evidence: define exit conditions.
- Too many milestones create overhead: keep decision value.

## Handoffs

QA defines evidence; engineering confirms readiness; Product Manager validates outcome meaning.
