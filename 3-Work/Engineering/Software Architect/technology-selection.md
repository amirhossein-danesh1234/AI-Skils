# Technology Selection

Context: [Software Architect](README.md).

## Purpose

Choose a technology against real requirements and lifecycle constraints.

## Activate When

A consequential dependency, platform, or tool choice is due.

## Do Not Use When

Do not replace a working stack for novelty or use vendor claims as verified performance.

## Required Context

**Needed:** Use case, hard constraints, existing stack, team capability, and support horizon.

**Can be deferred or bounded:** Shortlists can use public information; final choice needs current version/licensing and a proof of the uncertain requirement.

## Workflow

1. Inspect existing tools and the simplest option before introducing a new dependency.
2. Define hard requirements for capability, security, licensing, compatibility, and operation.
3. Compare viable options on total cost, maturity, ecosystem, team fit, lock-in, and reversibility.
4. Run a bounded proof on the most uncertain requirement using current official documentation.

## Decision Gate Ordering

Apply security, licensing, deployment, and capability exclusions before weighted preferences. Evaluate the difficult case in a bounded proof: migration, failure, upgrade, data export, or actual workload. Include exit and skill-acquisition cost; do not let a polished quickstart establish operational suitability.

## Decision Rules

- If an option fails a hard constraint, do not compensate with a high preference score.
- If uncertainty is material and testable cheaply, prototype before committing.

## Output Contract

Decision matrix or narrative with hard gates, evaluated options, proof results, risks, exit cost, and recommendation.

## Quality Gates

- Are versions, support claims, and license assumptions verified?
- Does the proof resemble the actual workload and include failure behavior?
- The selected option passes hard constraints and has a credible exit or containment path.

## Failure Modes

- Benchmark marketing accepted uncritically: reproduce relevant cases.
- Migration and exit cost omitted: include lifecycle cost.

## Handoffs

Security reviews supply-chain and compliance risk; DevOps checks operation; engineers test integration; owner approves spend.
