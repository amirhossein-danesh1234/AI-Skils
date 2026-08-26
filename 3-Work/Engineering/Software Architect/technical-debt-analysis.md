# Technical Debt Analysis

Context: [Software Architect](README.md).

## Purpose

Evaluate structural debt by its future cost, risk, and opportunity cost.

## Activate When

A team proposes refactoring or accumulated friction threatens delivery.

## Do Not Use When

Do not label every old technology or personal preference as debt.

## Required Context

**Needed:** Concrete friction/incident examples, affected system, and likely future changes.

**Can be deferred or bounded:** Precise monetary estimates can be ranges; cosmetic dissatisfaction is not sufficient evidence of debt.

## Workflow

1. Inspect examples where the current design caused delay, defects, risk, or operational burden.
2. Distinguish intentional trade-offs, obsolete requirements, defects, and structural debt.
3. Estimate future exposure and compare fix, contain, replace, or leave options.
4. Tie remediation to upcoming changes and define measurable benefit and completion.

## Interest Mechanism

Describe how the current structure repeatedly creates cost: duplicated fixes, fragile releases, blocked tests, or incidents. Compare containment, opportunistic repair, replacement, and no action over the same horizon. Include migration risk and an observable reduction in the original friction as completion evidence.

## Decision Rules

- If no meaningful future cost is evidenced, defer cosmetic refactoring.
- If debt threatens integrity or security, prioritize risk containment independently of feature demand.

## Output Contract

Debt register with mechanism, evidence, consequence, remediation options, cost, and timing recommendation.

## Quality Gates

- Is each item linked to a concrete cost mechanism?
- Does the proposed work reduce that mechanism without expanding scope unnecessarily?
- A remediation proposal reduces a named cost mechanism instead of merely changing style.

## Failure Modes

- Refactor everything: bound the affected behavior.
- Sunk effort justifies continuation: compare future costs only.

## Handoffs

Engineering owners estimate fixes; Project Manager plans capacity; Product Manager weighs opportunity cost.
