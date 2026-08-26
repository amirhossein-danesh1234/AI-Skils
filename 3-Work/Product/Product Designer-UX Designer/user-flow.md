# User Flow

Context: [Product Designer-UX Designer](README.md).

## Purpose

Specify paths through a user task, including decisions and recovery.

## Activate When

A task needs clear navigation and state transitions before implementation.

## Do Not Use When

Journey mapping covers the wider experience; UI layout is a separate decision.

## Required Context

**Needed:** User goal, actors, entry/exit conditions, and authoritative state rules.

**Can be deferred or bounded:** Detailed layouts may wait; unresolved business transitions remain marked decision gaps.

## Workflow

1. Inspect existing behavior and identify the authoritative state for each step.
2. Trace the shortest valid path to the user outcome.
3. Add branches for missing data, cancellation, denial, timeout, repeated actions, and return visits.
4. Review navigation, back behavior, saved progress, and consistency across entry points.

## Path Walkthrough

Trace a first visit, a return via deep link, a stale tab, and an interrupted submission. For each, show which state is restored, which permissions are rechecked, and how the user exits. Name terminal success, recoverable failure, and blocked states instead of leaving unlabeled arrows.

## Decision Rules

- If two states look identical but allow different actions, expose the difference to the user.
- If a step does not change information, consent, or control, consider removing it.

## Output Contract

Flow with entry and exit conditions, decisions, states, errors, permissions, and recovery paths.

## Quality Gates

- Can every path terminate, recover, or clearly explain a block?
- Do frontend and backend state assumptions agree?
- Every reachable branch ends in success, a safe recovery, or an understandable owned block.

## Failure Modes

- Screen sequence without decision logic: annotate conditions.
- Dead ends after errors: define recovery or support.

## Handoffs

Product Manager resolves business rules; Backend Engineer checks state transitions; Frontend Engineer implements navigation.
