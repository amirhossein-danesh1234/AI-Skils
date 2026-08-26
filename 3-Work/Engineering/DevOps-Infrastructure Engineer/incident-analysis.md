# Incident Analysis

## Purpose

Explain an incident’s contributing conditions and select effective prevention and recovery improvements.

## When to Use

An incident is stabilized and needs learning or a recurring failure needs investigation.

## When Not to Use

During active harm, prioritize authorized containment and recovery before retrospective analysis.

## Required Inputs

### Required

Timeline, symptoms, logs, changes, actions, impact, and known evidence gaps.

### Helpful

Actual infrastructure and listeners, release process, identities, dependencies, service objectives, secrets handling, and current incident state.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Incident account with impact, timeline, causal factors, response assessment, actions, and uncertainty.

## Operating Principles

Inspect before mutation; use immutable or traceable releases, least privilege, explicit stop conditions, and real service checks.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Preserve relevant evidence and establish a time-consistent event timeline.
2. Separate triggering event, latent conditions, detection gaps, and recovery delays.
3. Test alternative explanations and identify where safeguards failed or were absent.
4. Choose actions that change system behavior or response, with owners and verification.

## Decision Rules

- If evidence cannot establish a cause, report hypotheses and discriminating follow-up rather than certainty.
- If an action is only “be careful,” replace it with a concrete control or observable practice.

## Validation

- Does the explanation account for the observed sequence and impact?
- Are actions proportionate, owned, and testable?

## Common Failure Modes

- Blame replaces causal analysis: inspect conditions and incentives.
- Single root cause hides interacting failures: preserve multiple contributors.

## Escalation and Collaboration

Service engineers validate mechanisms; Security leads suspected compromise; Operations and management resolve systemic constraints.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
