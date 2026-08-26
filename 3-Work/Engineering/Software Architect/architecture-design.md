# Architecture Design

## Purpose

Choose a system structure that meets explicit functional and quality scenarios.

## When to Use

A new system or material structural change needs an architectural decision.

## When Not to Use

Do not redesign a system for a local defect or substitute architecture for product requirements.

## Required Inputs

### Required

Current system and code, business invariants, quality scenarios, expected load, team capacity, budget, and constraints.

### Helpful

Current topology and code, domain rules, load evidence, quality targets, team capabilities, constraints, and migration context.

### Optional

Previous decisions, comparable cases, or preferred output format. Their absence must not block a bounded first pass.

If a required fact is missing, identify which decision it affects. Continue with a labeled assumption only when the consequence is low risk and reversible; otherwise ask the smallest question needed. Do not invent project facts, approvals, measurements, or test results.

## Output

Architecture proposal with boundaries, data ownership, flows, alternatives, failure behavior, migration, risks, and decision record.

## Operating Principles

Prefer a modular single deployment when adequate. Introduce distribution or abstraction only for demonstrated needs, with observable failure and recovery behavior.

Separate verified facts, supplied information, external evidence, assumptions, estimates, inferences, opinions, and unknowns. Show the basis of consequential claims. Scale rigor to team capacity and risk; a framework is optional, and its limitations must be stated when used.

## Workflow

1. Inspect existing topology, deployment, dependencies, and observed failure or scaling constraints.
2. Translate requirements into testable scenarios for latency, availability, consistency, security, recovery, and cost.
3. Compare the simplest viable baseline with alternatives; include operational burden and team competence.
4. Define responsibilities, contracts, data ownership, synchronous and asynchronous flows, and failure containment.
5. Design incremental migration, compatibility, validation, and reversal or recovery before recommending adoption.

## Architecture Decision Packet

Describe the current system before the target: users and external systems, modules or services, deployment units, data stores, authoritative owners, and trust boundaries. Identify the specific observed or required scenario that the current system cannot satisfy.

For each candidate, walk a representative read, a state-changing operation, and a failure path. State where validation, authorization, atomicity, idempotency, and audit evidence live. Show synchronous dependencies, asynchronous handoffs, consistency and freshness guarantees, timeout budgets, retry limits, and what happens when a dependency is slow rather than completely unavailable.

Compare at least the simplest feasible baseline with the proposed structure. Evaluate total lifecycle cost: implementation, migration, on-call load, observability, data repair, dependency upgrades, team learning, and eventual exit. A distributed design must justify its network and coordination costs with a requirement that simpler modularity cannot satisfy.

Define evolution stages: compatible introduction, traffic or data transition, reconciliation, validation, retirement, and rollback limitations. If old and new code coexist, specify which versions can read and write each representation. A deployment rollback cannot restore destroyed data; identify restore or forward-repair requirements separately.

Attach a verification matrix mapping each important quality scenario to a test or evidence source. Examples include tenant isolation, duplicate payment requests, dependency timeout, restore from backup, and burst load; select only scenarios relevant to the actual system. Record unresolved assumptions and the person authorized to accept residual risk. Conclude with an ADR and implementation slices, not merely a diagram.

## Decision Rules

- If a modular single deployment meets requirements, do not add services merely for future scale.
- If a choice creates distributed consistency, require explicit invariants, failure semantics, and operational ownership.

## Validation

- Can each structural choice be traced to a requirement or demonstrated constraint?
- Have representative failure, overload, and recovery scenarios been walked end to end?

## Common Failure Modes

- Technology diagram without behavior: define contracts and failure paths.
- Speculative scale dominates current needs: document triggers for later evolution.

## Escalation and Collaboration

Backend and Database Engineers validate implementation and integrity; Security evaluates threats; DevOps checks operation; QA defines verification.

Do not perform external writes, production changes, purchases, disclosures, or commitments merely because this protocol recommends them. Confirm the actual task authorizes the action and stop at the boundary of that authority.

## Completion Criteria

The defined output answers the activation question; its decision rules and validation checks have been applied. Explicitly separate a proposal from an approved decision and a planned test from an observed result. Record the recommendation or changed artifact, the validation actually performed, remaining uncertainty, and the next action with an owner or proposed owner. Include priority, dependency, and definition of done when work remains. A blocked execution can produce a useful assessment, but it is not a completed implementation.
