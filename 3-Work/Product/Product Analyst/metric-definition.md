# Metric Definition

## Purpose

Specify a product metric so independent calculations agree.

## When to Use

A decision uses an ambiguous measure or instrumentation is being designed.

## When Not to Use

KPI design selects a decision system; this skill defines one measure precisely.

## Required Inputs

### Required

Decision question, event sources, identity rules, population, time window, and business meaning.

### Helpful

Decision question, event and identity definitions, time windows, source access, instrumentation history, and relevant product changes.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Metric contract with grain, formula, denominator, eligibility, exclusions, time semantics, source, owner, and limitations.

## Operating Principles

Preserve grain and exposure definitions, reconcile counts, and report null or inconclusive findings as readily as positive ones.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect raw events and confirm what each event actually records.
2. Define entity grain, deduplication, identity stitching, time zone, and late-arrival treatment.
3. Specify numerator and denominator from the same eligible population and observation window.
4. Calculate examples and edge cases, then reconcile against independent totals.

## Decision Rules

- If the event represents an attempt rather than success, do not label it completion.
- If identity or eligibility changes, version the definition before comparing trends.

## Validation

- Can another analyst reproduce the value from the contract?
- Are zero denominators, duplicates, and incomplete windows handled?

## Common Failure Modes

- Metric name hides changing formula: version it.
- Incompatible numerator and denominator: align eligibility.

## Escalation and Collaboration

Product Manager defines decision meaning; engineers confirm instrumentation; Financial Analyst owns financial metric treatment.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
