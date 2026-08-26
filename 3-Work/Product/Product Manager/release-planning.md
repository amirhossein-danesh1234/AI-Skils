# Release Planning

Context: [Product Manager](README.md).

## Purpose

Define a bounded product release, readiness conditions, and learning plan.

## Activate When

A product increment is approaching users or needs phased exposure.

## Do Not Use When

DevOps owns deployment mechanics; Project Manager owns schedule coordination; QA owns test evidence.

## Required Context

**Needed:** Candidate scope, intended audience, acceptance, and material exposure.

**Can be deferred or bounded:** Exact communications can follow a release-intent draft; readiness evidence and an authorized release owner are needed before exposure.

## Workflow

1. Inspect scope consistency and separate code availability from user-visible launch.
2. Identify audience, migration or onboarding needs, support instructions, and contractual commitments.
3. Define readiness gates and phased exposure proportional to harm and reversibility.
4. Align owners for observation, rollback decisions, customer communication, and outcome review.

## Launch Versus Deploy

Name which audiences can access which behavior and how activation is controlled. For each gate, record evidence owner, observation window, stop trigger, and who may promote or pause. Include customer/support promises and a scheduled outcome review; code rollback alone may not reverse customer commitments.

## Decision Rules

- If essential support, measurement, or safety readiness is missing, hold affected exposure.
- If risk is uncertain but bounded, use a limited pilot with explicit stop criteria.

## Output Contract

Release brief with audience, scope, gates, communication, rollout intent, monitoring, and stop conditions.

## Quality Gates

- Are every gate and stop condition observable and owned?
- Do release claims match actual enabled capabilities?
- A pilot has a bounded audience and a real owner able to stop exposure.

## Failure Modes

- Deploy equals launch: separate operations from product exposure.
- No post-launch owner: assign monitoring and review responsibility.

## Handoffs

DevOps plans safe rollout; QA reports confidence; Marketing and Sales align truthful communication.
