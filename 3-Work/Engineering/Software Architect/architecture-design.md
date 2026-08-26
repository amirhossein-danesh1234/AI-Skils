# Architecture Design

Context: [Software Architect](README.md).

## Purpose

Choose a system structure that meets explicit functional and quality scenarios.

## Activate When

A new system or material structural change needs an architectural decision.

## Do Not Use When

Do not redesign a system for a local defect or substitute architecture for product requirements.

## Required Context

**Needed:** Current system, approved behavior/invariants, driving quality scenarios, and team constraints.

**Can be deferred or bounded:** Unknown scale can be a bounded workload hypothesis; irreversible data and trust decisions need explicit owners.

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

## Architecture Versus AI Behavior

For AI-enabled components, keep deterministic system guarantees separate from probabilistic task quality. Define the service boundary and failure isolation here; request AI Engineer evaluation evidence before trusting model behavior. A small modular baseline remains a real candidate even when the proposed feature uses agents.

## Decision Rules

- If a modular single deployment meets requirements, do not add services merely for future scale.
- If a choice creates distributed consistency, require explicit invariants, failure semantics, and operational ownership.

## Output Contract

Architecture proposal with boundaries, data ownership, flows, alternatives, failure behavior, migration, risks, and decision record.

## Quality Gates

- Can each structural choice be traced to a requirement or demonstrated constraint?
- Have representative failure, overload, and recovery scenarios been walked end to end?
- Every new deployment or storage boundary has a demonstrated driver and an operator.

## Failure Modes

- Technology diagram without behavior: define contracts and failure paths.
- Speculative scale dominates current needs: document triggers for later evolution.

## Handoffs

Backend and Database Engineers validate implementation and integrity; Security evaluates threats; DevOps checks operation; QA defines verification.
