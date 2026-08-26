# Architecture Review

## Purpose

Assess an existing or proposed architecture against its actual requirements and risks.

## When to Use

A design needs an independent structural critique or readiness decision.

## When Not to Use

Architecture-design.md creates alternatives; code review checks local implementation.

## Required Inputs

### Required

Architecture artifacts, actual code and deployments, quality targets, constraints, and review scope.

### Helpful

Current topology and code, domain rules, load evidence, quality targets, team capabilities, constraints, and migration context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Prioritized findings with evidence, violated scenario, consequence, alternatives, and acceptance or remediation conditions.

## Operating Principles

Prefer a modular single deployment when adequate. Introduce distribution or abstraction only for demonstrated needs, with observable failure and recovery behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Reconstruct the system from authoritative artifacts and note differences from diagrams.
2. Trace critical requests, state changes, dependencies, and recovery paths.
3. Challenge assumptions about consistency, scale, security, and operational capacity.
4. Rank findings by impact and likelihood; recommend minimal structural corrections and residual-risk owners.

## Decision Rules

- If a claim lacks load or failure evidence, mark it unverified rather than automatically wrong.
- If a local fix solves the risk, avoid recommending wholesale redesign.

## Validation

- Are findings reproducible or tied to an explicit scenario?
- Are strengths, limitations, and unreviewed areas distinguished?

## Common Failure Modes

- Preferred stack becomes a review criterion: use requirements.
- Checklist score hides critical weakness: prioritize consequences.

## Escalation and Collaboration

Consult discipline engineers for evidence; the decision owner accepts residual architectural risk.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
