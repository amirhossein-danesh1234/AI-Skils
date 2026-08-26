# State Management

Context: [Frontend Engineer](README.md).

## Purpose

Model client state so transitions remain correct under asynchronous interaction.

## Activate When

A UI has stale data, duplicated state, or unclear transition ownership.

## Do Not Use When

Do not duplicate server authority or add a global store without a sharing need.

## Required Context

**Needed:** State values, events, authoritative sources, and async operations.

**Can be deferred or bounded:** A state diagram is optional for simple components; invalid combinations and transition ownership must still be clear.

## Workflow

1. List each state value and classify server, URL, persistent, or local ownership.
2. Remove values derivable from authoritative state and define valid combinations.
3. Model events and asynchronous transitions including cancellation, retry, and stale responses.
4. Test rapid changes, navigation, remounts, optimistic failure, and concurrent requests.

## Transition Stress

For each async event, define request identity, pending state, cancellation, stale-result handling, and error rollback. Derive values where possible rather than synchronizing copies. Test rapid edits, route changes, optimistic failure, and permission changes while the component remains mounted.

## Decision Rules

- If a value can be derived reliably, compute it rather than synchronizing a second copy.
- If a response belongs to an obsolete request, ignore or cancel it rather than overwrite newer state.

## Output Contract

State model with source of truth, transitions, derived values, synchronization, and tests.

## Quality Gates

- Can impossible state combinations occur?
- Does retry or rollback restore consistent visible and server state?
- Only the current authoritative response may commit a state transition.

## Failure Modes

- Multiple sources of truth drift: choose authority.
- Boolean explosion obscures states: use an explicit transition model where helpful.

## Handoffs

Backend Engineer defines server guarantees; UX Designer defines user-visible recovery; [frontend-architecture.md](frontend-architecture.md) handles broader boundaries.
