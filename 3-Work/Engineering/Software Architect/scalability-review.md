# Scalability Review

## Purpose

Find the limiting resource or coordination path under a realistic workload.

## When to Use

Growth or load threatens required service performance.

## When Not to Use

Do not recommend sharding or caching without measuring the actual bottleneck.

## Required Inputs

### Required

Workload shape, growth scenarios, latency targets, resource data, topology, and cost constraints.

### Helpful

Current topology and code, domain rules, load evidence, quality targets, team capabilities, constraints, and migration context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Capacity model, bottlenecks, failure thresholds, options, load-test plan, and scaling triggers.

## Operating Principles

Prefer a modular single deployment when adequate. Introduce distribution or abstraction only for demonstrated needs, with observable failure and recovery behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect throughput, concurrency, payload size, skew, hot keys, and background work.
2. Map resource demand and serialized sections along critical paths.
3. Estimate headroom and test representative load including bursts and dependency slowdown.
4. Compare optimization, capacity increase, caching, queueing, and partitioning with cost and complexity.

## Decision Rules

- If the bottleneck is a shared serialized operation, adding stateless instances may not help.
- If observed demand is below limits, define monitoring triggers instead of premature redesign.

## Validation

- Does the load model include skew, warmup, and realistic data volume?
- Are tail latency, saturation, errors, and recovery measured together?

## Common Failure Modes

- Average load hides hotspots: test distribution.
- Linear scaling assumed: measure contention and coordination.

## Escalation and Collaboration

Backend and Database Engineers profile hotspots; DevOps runs safe load tests; Product Manager confirms user targets.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
