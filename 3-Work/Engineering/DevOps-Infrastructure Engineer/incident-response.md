# Incident Response

Context: [DevOps-Infrastructure Engineer](README.md).

## Purpose

Coordinate safe containment and recovery during an active production incident.

## Activate When

Users are suffering a current outage, integrity failure, suspected compromise, or uncontrolled operational cost.

## Do Not Use When

incident-analysis is for learning after stabilization; this protocol does not itself authorize production changes or replace an existing incident command.

## Required Context

**Needed:** Observed impact, target service/environment, current incident owner, available signals, and authorized response scope.

**Can be deferred or bounded:** Root cause is not required before safe containment. Missing access or authority requires urgent escalation with a concrete action request, not speculative changes.

## Workflow

1. Confirm the affected environment and current user impact; open or join the existing incident coordination path. Establish one incident commander and separate operational action from stakeholder communication, combining roles for a small team when practical.
2. Capture a time-stamped state summary and recent change context. Freeze unrelated changes within the incident mandate and prevent conflicting simultaneous interventions. Preserve evidence without delaying necessary containment.
3. Choose the lowest-risk authorized containment: reduce exposure, disable the affected feature, shed load, isolate a compromised component, or revert compatible code. Check effects on data integrity, customers, and essential access before acting.
4. Record each action, owner, hypothesis, expected signal, and abort condition. Compare observations with the expected effect; stop an ineffective or harmful action rather than stacking uncontrolled changes.
5. Verify recovery through real critical operations, integrity/reconciliation checks, and an observation window appropriate to traffic. A healthy process or green HTTP endpoint alone is insufficient.
6. Hand off remaining risks, watch duties, customer/obligation follow-up, and evidence to incident-analysis after stability. Declare recovery only through the existing authorized incident process.

## Decision Rules

- If compromise or sensitive data exposure is suspected, bring Security into containment immediately and preserve evidence; legal notification decisions need the qualified owner.
- If rollback cannot undo a data or external side effect, use the prepared recovery/reconciliation path; do not blindly replay writes.
- If no authorized safe action is available, escalate impact, exact target, proposed action, and consequence of delay.

## Output Contract

Live incident record: impact/time, commander and responders, action log, containment choice, current state, next checkpoint, recovery evidence, and explicit handoff.

## Quality Gates

- Recovery is supported by user-operation and integrity evidence, not only infrastructure health.
- Concurrent responders share one action record and unresolved risk has a named owner.
- Restore/replay did not create duplicate external effects or overwrite unreviewed live state.

## Failure Modes

- Root-cause debate delays available safe containment.
- Several responders change the same system without coordination.
- Temporary recovery is declared permanent without observation or data reconciliation.

## Handoffs

Security leads security-specific containment; Backend/Database diagnose effects and integrity; Product Manager bounds user exposure; authorized communications owner handles external claims.

## References

[Google SRE incident response](https://sre.google/workbook/incident-response/) informs command, communication, and operational separation. Scale staffing to the team and follow the existing incident process.
