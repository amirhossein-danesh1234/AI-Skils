# Interaction Design

Context: [Product Designer-UX Designer](README.md).

## Purpose

Define how controls respond to user intent and system state.

## Activate When

A flow needs concrete interaction behavior and feedback.

## Do Not Use When

Do not decide visual tokens or backend policy under the guise of interaction design.

## Required Context

**Needed:** Control intent, allowed state transitions, and input methods.

**Can be deferred or bounded:** Animation and detailed visual tokens can wait; destructive-action consequences cannot.

## Workflow

1. Inspect user intent and the system response behind each control.
2. Specify action availability, input validation timing, loading, success, failure, and cancellation.
3. Design keyboard, touch, pointer, and assistive-technology behavior as relevant.
4. Test accidental activation, repeat actions, delayed responses, and destructive operations.

## Interaction State Table

Record event, current state, permitted action, next state, feedback, focus destination, and recovery. Distinguish validation during typing from validation on submission. Check double activation, delayed response, dismissal, and focus return after overlays; confirmation should explain the actual consequence rather than merely ask if the user is sure.

## Decision Rules

- If an action is irreversible or costly, provide proportional confirmation or recovery.
- If an operation is delayed, expose progress without implying completion.

## Output Contract

Interaction specification with triggers, feedback, state changes, focus behavior, errors, and reversibility.

## Quality Gates

- Can users understand whether an action occurred and what to do next?
- Are focus and control semantics consistent across states?
- The state table specifies who announces asynchronous success or error and where focus remains.

## Failure Modes

- Animation replaces feedback: show actual state.
- Disabled control gives no reason: explain constraints or prerequisites.

## Handoffs

UI Designer specifies visual states; Frontend Engineer verifies semantics; Backend Engineer confirms operation guarantees.
