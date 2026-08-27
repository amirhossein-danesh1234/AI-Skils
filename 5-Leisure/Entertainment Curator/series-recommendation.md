# series-recommendation

[Entertainment Curator](README.md) / [Leisure domain](../../README.md)

## Curation Goal

Match a series to taste, episode/season commitment and viewing context.

## Activate For

The user needs a series that fits taste and commitment tolerance.

## Taste Boundary

Does not ignore cancellation status, episode length or availability when those matter.

## Preference Context

Liked/disliked series with reasons, genres/tone, episode and total commitment, pacing, ongoing/completed preference, content limits, co-viewers, region/platform and novelty.

## Curation Workflow

1. Translate examples into pacing, serialization, character focus, procedural versus arc, tone and commitment signals.
2. Screen candidates for episode length, seasons, completion/cancellation status and audience/content fit; verify current status and availability when material.
3. Compare a few choices including a low-commitment option, explain the opening commitment without spoilers and flag slow-start trade-offs.
4. Recommend a first pick with a trial rule such as an episode checkpoint and a fallback with a different pacing/commitment profile.

## Commitment Profile

Distinguish episode duration, number of seasons, narrative closure, attention demand and time until the show reveals its form. “Long” is several different burdens.

## Curation Rules

- Do not recommend an unfinished/cancelled story as complete.
- Current catalog availability and renewal status require verification.

## Recommendation Output

Series shortlist with fit, episode/season commitment, status, pacing, spoiler-safe caveats, access check and trial/fallback.

## Fit Checks

- Options fit stated time and completion tolerance.
- The trial rule does not demand a season before reassessment.

## Curation Failure Modes

- **Prestige list ignores commitment:** profile it.
- **Slow start hidden to force recommendation:** disclose trade-off.

## Handoffs

Movie Recommendation handles one-session viewing; Group Activity handles co-viewing; Mood-Based refines tone.
