# Interaction Design

## Purpose

Define how controls respond to user intent and system state.

## When to Use

A flow needs concrete interaction behavior and feedback.

## When Not to Use

Do not decide visual tokens or backend policy under the guise of interaction design.

## Required Inputs

### Required

Approved flow, control purpose, input methods, constraints, and state model.

### Helpful

User tasks, research evidence, current screens and flows, constraints, accessibility needs, and business rules.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Interaction specification with triggers, feedback, state changes, focus behavior, errors, and reversibility.

## Operating Principles

Separate observed behavior from interpretation. Optimize comprehension and task completion, not screen count or visual novelty.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect user intent and the system response behind each control.
2. Specify action availability, input validation timing, loading, success, failure, and cancellation.
3. Design keyboard, touch, pointer, and assistive-technology behavior as relevant.
4. Test accidental activation, repeat actions, delayed responses, and destructive operations.

## Decision Rules

- If an action is irreversible or costly, provide proportional confirmation or recovery.
- If an operation is delayed, expose progress without implying completion.

## Validation

- Can users understand whether an action occurred and what to do next?
- Are focus and control semantics consistent across states?

## Common Failure Modes

- Animation replaces feedback: show actual state.
- Disabled control gives no reason: explain constraints or prerequisites.

## Escalation and Collaboration

UI Designer specifies visual states; Frontend Engineer verifies semantics; Backend Engineer confirms operation guarantees.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
