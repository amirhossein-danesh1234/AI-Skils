# State Management

## Purpose

Model client state so transitions remain correct under asynchronous interaction.

## When to Use

A UI has stale data, duplicated state, or unclear transition ownership.

## When Not to Use

Do not duplicate server authority or add a global store without a sharing need.

## Required Inputs

### Required

State inventory, events, data sources, persistence needs, and navigation behavior.

### Helpful

Repository instructions, approved UI and behavior, runtime versions, API contracts, existing tests, and supported devices.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

State model with source of truth, transitions, derived values, synchronization, and tests.

## Operating Principles

Follow existing conventions, keep state minimal, test realistic interactions, and distinguish compilation from verified user behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. List each state value and classify server, URL, persistent, or local ownership.
2. Remove values derivable from authoritative state and define valid combinations.
3. Model events and asynchronous transitions including cancellation, retry, and stale responses.
4. Test rapid changes, navigation, remounts, optimistic failure, and concurrent requests.

## Decision Rules

- If a value can be derived reliably, compute it rather than synchronizing a second copy.
- If a response belongs to an obsolete request, ignore or cancel it rather than overwrite newer state.

## Validation

- Can impossible state combinations occur?
- Does retry or rollback restore consistent visible and server state?

## Common Failure Modes

- Multiple sources of truth drift: choose authority.
- Boolean explosion obscures states: use an explicit transition model where helpful.

## Escalation and Collaboration

Backend Engineer defines server guarantees; UX Designer defines user-visible recovery; frontend-architecture.md handles broader boundaries.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
