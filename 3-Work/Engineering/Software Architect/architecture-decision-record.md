# Architecture Decision Record

Context: [Software Architect](README.md).

## Purpose

Record a consequential technical choice and the conditions behind it.

## Activate When

A structural decision needs durable context for future maintainers.

## Do Not Use When

Do not use an ADR as a design tutorial or retroactively invent unanimous approval.

## Required Context

**Needed:** Decision question, alternatives actually considered, evidence, and decision status.

**Can be deferred or bounded:** A proposed record can precede approval; never invent the historic rationale or participants.

## Workflow

1. Inspect existing ADR conventions and related decisions.
2. State the problem and constraints at the time of choice.
3. Summarize credible alternatives and why they were rejected.
4. Record the chosen option, trade-offs, unresolved risks, and supersession or review conditions.

## Decision Revisit

Include a concrete condition that would invalidate the choice and link affected contracts or quality scenarios. Preserve dissent and rejected alternatives when they explain risk. Supersede old decisions rather than rewriting them to make the current system appear inevitable.

## Decision Rules

- If the decision is proposed, label it proposed rather than accepted.
- If context materially changes, supersede the record instead of erasing history.

## Output Contract

ADR with context, options, decision, consequences, status, owner, date, and revisit triggers.

## Quality Gates

- Could a future engineer understand why the choice was reasonable?
- Are links, evidence, status, and consequences accurate?
- A future maintainer can distinguish original constraints from assumptions that have since changed.

## Failure Modes

- Decision without alternatives: preserve the trade-off.
- Revision rewrites history: add a new status or superseding record.

## Handoffs

Relevant engineering owners review consequences; decision authority confirms acceptance.
