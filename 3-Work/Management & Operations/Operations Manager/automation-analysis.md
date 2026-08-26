# Automation Analysis

## Purpose

Decide whether a recurring task should be automated and under what controls.

## When to Use

Manual effort or errors suggest automation.

## When Not to Use

Do not automate unstable policy, unclear ownership, or rare work without a cost case.

## Required Inputs

### Required

Task volume, variability, error cost, rules, systems, data sensitivity, and maintenance capacity.

### Helpful

Actual work samples, process boundaries, volumes, timing, defects, roles, tools, and service expectations.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Automation assessment with suitability, alternatives, economics, exceptions, oversight, pilot, and stop conditions.

## Operating Principles

Improve end-to-end flow and quality, not one team’s utilization at the expense of downstream queues.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Observe the manual workflow and identify stable rules and variable judgment.
2. Compare elimination or simplification with automation.
3. Estimate build, integration, monitoring, exception, and maintenance cost against actual benefit.
4. Define human review, failure recovery, permissions, and a bounded pilot.

## Decision Rules

- If inputs or policy are unstable, stabilize them before automating.
- If automation can create irreversible harm, require appropriate approval and verification controls.

## Validation

- Are exceptions and maintenance ownership explicit?
- Does the business case include failure and oversight cost?

## Common Failure Modes

- Time-saving claim ignores exceptions: model total effort.
- Automation removes accountability: retain an owner.

## Escalation and Collaboration

Engineers assess implementation; Security reviews permissions; Financial Analyst checks economics; no AI Engineer persona is assumed available.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
