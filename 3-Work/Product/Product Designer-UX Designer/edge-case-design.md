# Edge Case Design

## Purpose

Specify user-facing behavior when ordinary assumptions fail.

## When to Use

A flow has incomplete error, boundary, concurrency, or permission behavior.

## When Not to Use

QA edge-case-analysis.md discovers test coverage; this skill chooses coherent user behavior with approved policy.

## Required Inputs

### Required

Flow, state model, rules, limits, roles, external dependencies, and destructive actions.

### Helpful

User tasks, research evidence, current screens and flows, constraints, accessibility needs, and business rules.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Edge-state catalog with trigger, user message, allowed actions, persistence, recovery, and owner.

## Operating Principles

Separate observed behavior from interpretation. Optimize comprehension and task completion, not screen count or visual novelty.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Enumerate empty and oversized data, invalid input, interruption, delay, denial, duplication, and conflicting updates.
2. Identify which state is authoritative and what the user can safely retry or undo.
3. Design feedback that explains the consequence without exposing sensitive internals.
4. Walk return visits and partial completion to ensure the user can recover without repeating unsafe actions.

## Decision Rules

- If retry can duplicate a side effect, require backend guarantees before offering it.
- If policy is unclear, record the decision rather than inventing an error outcome.

## Validation

- Does each important failure have a safe and understandable next action?
- Are recovery states consistent with persisted server state?

## Common Failure Modes

- Generic error for every case: distinguish actionable causes.
- Frontend recovery assumes backend guarantees: verify the contract.

## Escalation and Collaboration

Backend Engineer defines consistency and idempotency; Product Manager approves policy; QA turns states into tests.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
