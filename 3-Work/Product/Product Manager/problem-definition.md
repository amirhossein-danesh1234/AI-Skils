# Problem Definition

Context: [Product Manager](README.md).

## Purpose

Establish a supported user problem before selecting a solution.

## Activate When

A request, complaint, or opportunity is too vague to justify product work.

## Do Not Use When

Do not write a feature specification until the problem and desired outcome are sufficiently clear.

## Required Context

**Needed:** A user situation, observed or reported unmet outcome, and the decision being considered.

**Can be deferred or bounded:** Frequency can remain unknown until measured; a single case still permits a bounded problem hypothesis.

## Workflow

1. Inspect real examples, support records, research, and current behavior rather than accepting the requested solution as the problem.
2. Identify the job, trigger, expected outcome, workaround, and cost of failure for the primary segment.
3. Separate symptoms from causes and distinguish customer pain from internal preference.
4. Compare no action, process, content, UX, operations, automation, and feature paths; choose the next evidence step.

## Problem Evidence Ladder

Separate request, observed behavior, repeated pattern, and quantified prevalence. Count distinct affected accounts rather than tickets when the decision is account-level. Seek a disconfirming case where the same situation succeeds, then test whether the obstacle is policy, comprehension, reliability, or missing capability.

## Decision Rules

- If no affected user or observable consequence can be identified, do not advance directly to build.
- If a low-cost workaround meets the outcome, test it before proposing software.

## Output Contract

Problem statement, affected users, frequency and severity, desired outcome, assumptions, and evidence gaps.

## Quality Gates

- Can someone recognize an actual occurrence and judge whether it improved?
- Are assumptions labeled and conflicting evidence included?
- The statement describes a recognizable failure independent of the proposed solution.

## Failure Modes

- Restating the solution as a problem: describe the unmet outcome.
- Single anecdote generalized: bound confidence and seek representative evidence.

## Handoffs

UX Designer investigates behavior; Product Analyst checks frequency; Product Strategist checks whether the problem fits direction.
