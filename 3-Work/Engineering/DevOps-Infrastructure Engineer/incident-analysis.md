# Incident Analysis

Context: [DevOps-Infrastructure Engineer](README.md).

## Purpose

Explain an incident’s contributing conditions and select effective prevention and recovery improvements.

## Activate When

An incident is stabilized and needs learning or a recurring failure needs investigation.

## Do Not Use When

Use [incident-response.md](incident-response.md) for active harm and authorized containment; retrospective causal analysis follows stabilization.

## Required Context

**Needed:** Stabilized incident timeline, impact, evidence, actions, and uncertainties.

**Can be deferred or bounded:** Causality may remain unresolved; useful improvement proposals can target demonstrated detection or recovery gaps.

## Workflow

1. Preserve relevant evidence and establish a time-consistent event timeline.
2. Separate triggering event, latent conditions, detection gaps, and recovery delays.
3. Test alternative explanations and identify where safeguards failed or were absent.
4. Choose actions that change system behavior or response, with owners and verification.

## Causal Counterfactual

For each contributing factor, ask whether changing it would have prevented or reduced the observed impact. Separate trigger, latent condition, detection delay, and recovery delay. Choose a few actions with verification, not a long list of generic hardening or a requirement for someone to be more careful.

## Decision Rules

- If evidence cannot establish a cause, report hypotheses and discriminating follow-up rather than certainty.
- If an action is only “be careful,” replace it with a concrete control or observable practice.

## Output Contract

Incident account with impact, timeline, causal factors, response assessment, actions, and uncertainty.

## Quality Gates

- Does the explanation account for the observed sequence and impact?
- Are actions proportionate, owned, and testable?
- Every corrective action interrupts a demonstrated causal or response mechanism.

## Failure Modes

- Blame replaces causal analysis: inspect conditions and incentives.
- Single root cause hides interacting failures: preserve multiple contributors.

## Handoffs

Service engineers validate mechanisms; Security leads suspected compromise; Operations and management resolve systemic constraints.
