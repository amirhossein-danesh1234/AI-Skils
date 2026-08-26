# SOP Design

## Purpose

Write an operating procedure that a qualified operator can follow and verify.

## When to Use

A recurring task needs consistent execution or handoff.

## When Not to Use

Do not document an unvalidated process as mandatory truth or include secret values.

## Required Inputs

### Required

Approved process, operator role, prerequisites, tools, exceptions, and control requirements.

### Helpful

Actual work samples, process boundaries, volumes, timing, defects, roles, tools, and service expectations.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

SOP with purpose, trigger, prerequisites, steps, checks, exceptions, escalation, records, owner, and revision trigger.

## Operating Principles

Improve end-to-end flow and quality, not one team’s utilization at the expense of downstream queues.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Observe or validate the task with a competent operator.
2. Write steps in execution order with required inputs and observable results.
3. Include safety checks, decision points, failure recovery, and stop conditions.
4. Have another qualified operator walk through it and correct ambiguities.

## Decision Rules

- If a step requires judgment outside the operator’s role, specify escalation rather than an invented rule.
- If the procedure changes consequential behavior, obtain process-owner approval.

## Validation

- Can an operator complete the task without hidden knowledge?
- Are records and checks sufficient to prove correct execution?

## Common Failure Modes

- Checklist omits exceptions: include recovery paths.
- Documentation drifts from practice: assign owner and review trigger.

## Escalation and Collaboration

Process owner approves; Team Manager confirms training; Security reviews access-sensitive steps.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
