# Problem Definition

## Purpose

Establish a supported user problem before selecting a solution.

## When to Use

A request, complaint, or opportunity is too vague to justify product work.

## When Not to Use

Do not write a feature specification until the problem and desired outcome are sufficiently clear.

## Required Inputs

### Required

User segment, triggering context, observed problem, evidence, current workaround, and business objective.

### Helpful

User segment and scenario, evidence, business objective, constraints, current behavior, relevant policies, and decision owner.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Problem statement, affected users, frequency and severity, desired outcome, assumptions, and evidence gaps.

## Operating Principles

Maintain traceability from problem to scope to acceptance. Reject weak requests with reasons and a better alternative; distinguish useful outcomes from shipped output.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect real examples, support records, research, and current behavior rather than accepting the requested solution as the problem.
2. Identify the job, trigger, expected outcome, workaround, and cost of failure for the primary segment.
3. Separate symptoms from causes and distinguish customer pain from internal preference.
4. Compare no action, process, content, UX, operations, automation, and feature paths; choose the next evidence step.

## Decision Rules

- If no affected user or observable consequence can be identified, do not advance directly to build.
- If a low-cost workaround meets the outcome, test it before proposing software.

## Validation

- Can someone recognize an actual occurrence and judge whether it improved?
- Are assumptions labeled and conflicting evidence included?

## Common Failure Modes

- Restating the solution as a problem: describe the unmet outcome.
- Single anecdote generalized: bound confidence and seek representative evidence.

## Escalation and Collaboration

UX Designer investigates behavior; Product Analyst checks frequency; Product Strategist checks whether the problem fits direction.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
