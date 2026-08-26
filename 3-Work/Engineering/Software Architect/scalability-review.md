# Scalability Review

Context: [Software Architect](README.md).

## Purpose

Find the limiting resource or coordination path under a realistic workload.

## Activate When

Growth or load threatens required service performance.

## Do Not Use When

Do not recommend sharding or caching without measuring the actual bottleneck.

## Required Context

**Needed:** Representative workload, current measurements, quality limits, and topology.

**Can be deferred or bounded:** Future demand may be scenario ranges; do not claim measured capacity from an unrun load model.

## Workflow

1. Inspect throughput, concurrency, payload size, skew, hot keys, and background work.
2. Map resource demand and serialized sections along critical paths.
3. Estimate headroom and test representative load including bursts and dependency slowdown.
4. Compare optimization, capacity increase, caching, queueing, and partitioning with cost and complexity.

## Capacity Envelope

Model throughput, concurrency, payload size, hot-key skew, and serialized work together. Locate the knee where queues or tail latency rise, then test recovery after overload. Report sustainable capacity under the tested conditions and the monitoring trigger for another intervention, not an extrapolated infinite scale claim.

## Decision Rules

- If the bottleneck is a shared serialized operation, adding stateless instances may not help.
- If observed demand is below limits, define monitoring triggers instead of premature redesign.

## Output Contract

Capacity model, bottlenecks, failure thresholds, options, load-test plan, and scaling triggers.

## Quality Gates

- Does the load model include skew, warmup, and realistic data volume?
- Are tail latency, saturation, errors, and recovery measured together?
- The proposed change addresses the limiting resource rather than adding capacity elsewhere.

## Failure Modes

- Average load hides hotspots: test distribution.
- Linear scaling assumed: measure contention and coordination.

## Handoffs

Backend and Database Engineers profile hotspots; DevOps runs safe load tests; Product Manager confirms user targets.
