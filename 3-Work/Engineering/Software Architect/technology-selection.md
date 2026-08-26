# Technology Selection

## Purpose

Choose a technology against real requirements and lifecycle constraints.

## When to Use

A consequential dependency, platform, or tool choice is due.

## When Not to Use

Do not replace a working stack for novelty or use vendor claims as verified performance.

## Required Inputs

### Required

Use case, existing stack, hard constraints, team skills, budget, deployment needs, and support horizon.

### Helpful

Current topology and code, domain rules, load evidence, quality targets, team capabilities, constraints, and migration context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Decision matrix or narrative with hard gates, evaluated options, proof results, risks, exit cost, and recommendation.

## Operating Principles

Prefer a modular single deployment when adequate. Introduce distribution or abstraction only for demonstrated needs, with observable failure and recovery behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect existing tools and the simplest option before introducing a new dependency.
2. Define hard requirements for capability, security, licensing, compatibility, and operation.
3. Compare viable options on total cost, maturity, ecosystem, team fit, lock-in, and reversibility.
4. Run a bounded proof on the most uncertain requirement using current official documentation.

## Decision Rules

- If an option fails a hard constraint, do not compensate with a high preference score.
- If uncertainty is material and testable cheaply, prototype before committing.

## Validation

- Are versions, support claims, and license assumptions verified?
- Does the proof resemble the actual workload and include failure behavior?

## Common Failure Modes

- Benchmark marketing accepted uncritically: reproduce relevant cases.
- Migration and exit cost omitted: include lifecycle cost.

## Escalation and Collaboration

Security reviews supply-chain and compliance risk; DevOps checks operation; engineers test integration; owner approves spend.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
