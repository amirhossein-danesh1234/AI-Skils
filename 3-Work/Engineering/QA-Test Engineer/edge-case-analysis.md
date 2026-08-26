# Edge Case Analysis

## Purpose

Discover high-value boundary and failure scenarios missing from current coverage.

## When to Use

A feature’s happy path is defined but unusual conditions are underexplored.

## When Not to Use

UX edge-case-design.md chooses user behavior; this skill identifies risk and test needs.

## Required Inputs

### Required

State model, inputs, permissions, dependencies, limits, and existing tests.

### Helpful

Requirements, change diff, architecture, critical journeys, known defects, test environments, and release context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Prioritized edge-case inventory with trigger, expected invariant, impact, and test approach.

## Operating Principles

Prioritize impact, likelihood, change exposure, and usage; report skipped, blocked, flaky, and failed tests separately.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect boundaries in values, sizes, time, identity, concurrency, and lifecycle.
2. Combine plausible stressors such as timeout plus retry or permission change plus cached state.
3. Trace partial completion, duplicate events, cancellation, and recovery.
4. Prioritize by credible impact and identify undefined behavior for owner resolution.

## Decision Rules

- If a combination is impossible under enforced constraints, do not inflate the test plan with it.
- If an edge case can corrupt data or cross a trust boundary, prioritize it even when rare.

## Validation

- Are cases grounded in reachable states?
- Does every high-risk undefined behavior have an owner?

## Common Failure Modes

- Exotic cases crowd out common failure: rank by risk.
- Edge list without oracle: state the invariant to preserve.

## Escalation and Collaboration

UX and Product Manager define intended behavior; Backend and Database Engineers validate concurrency mechanisms.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
