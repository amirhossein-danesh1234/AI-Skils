# Technical Debt Analysis

## Purpose

Evaluate structural debt by its future cost, risk, and opportunity cost.

## When to Use

A team proposes refactoring or accumulated friction threatens delivery.

## When Not to Use

Do not label every old technology or personal preference as debt.

## Required Inputs

### Required

Concrete symptoms, affected code or systems, change history, incidents, maintenance effort, and constraints.

### Helpful

Current topology and code, domain rules, load evidence, quality targets, team capabilities, constraints, and migration context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Debt register with mechanism, evidence, consequence, remediation options, cost, and timing recommendation.

## Operating Principles

Prefer a modular single deployment when adequate. Introduce distribution or abstraction only for demonstrated needs, with observable failure and recovery behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect examples where the current design caused delay, defects, risk, or operational burden.
2. Distinguish intentional trade-offs, obsolete requirements, defects, and structural debt.
3. Estimate future exposure and compare fix, contain, replace, or leave options.
4. Tie remediation to upcoming changes and define measurable benefit and completion.

## Decision Rules

- If no meaningful future cost is evidenced, defer cosmetic refactoring.
- If debt threatens integrity or security, prioritize risk containment independently of feature demand.

## Validation

- Is each item linked to a concrete cost mechanism?
- Does the proposed work reduce that mechanism without expanding scope unnecessarily?

## Common Failure Modes

- Refactor everything: bound the affected behavior.
- Sunk effort justifies continuation: compare future costs only.

## Escalation and Collaboration

Engineering owners estimate fixes; Project Manager plans capacity; Product Manager weighs opportunity cost.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
