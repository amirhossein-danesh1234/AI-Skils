# book-recommendation

[Entertainment Curator](README.md) / [Leisure domain](../../README.md)

## Curation Goal

Recommend a small set of books fitted to reading taste, purpose and attention.

## Activate For

The user wants a book or short reading shortlist for a particular experience.

## Taste Boundary

Does not equate bestseller status or prestige with personal fit.

## Preference Context

Recent likes/dislikes with reasons, genres/themes, fiction/nonfiction, language/format, length and attention, content boundaries, desired novelty and access constraints.

## Curation Workflow

1. Extract taste signals from what worked and failed—voice, pace, complexity, themes, structure and emotional intensity—not only genre labels.
2. Define the reading context and desired experience, then generate candidates with distinct reasons rather than near-duplicates.
3. Verify bibliographic basics, edition/translation and current access only when material; screen content boundaries without spoilers.
4. Return a ranked shortlist of a few options, explain trade-offs and choose one starting recommendation plus a pivot if it misses.

## Taste Vector

Represent fit across prose/voice, pace, ideas versus plot, emotional tone, length/commitment, familiarity/novelty and content tolerance. A celebrated book may score poorly for the current moment.

## Curation Rules

- Prefer evidence from the user’s reaction to titles over generic popularity.
- Do not infer literary ability or identity from preferences.

## Recommendation Output

Shortlist with fit reasons, commitment, novelty, spoiler-free caveats, verified edition/access where needed, first pick and fallback.

## Fit Checks

- Options are meaningfully different and each maps to stated taste.
- No unsupported availability or content claim is presented as current fact.

## Curation Failure Modes

- **Twenty-title list shifts work to user:** narrow.
- **Genre match ignores disliked style:** use reaction details.

## Handoffs

Mood-Based Recommendation handles desired feeling; Activity Planner handles book-club logistics; Hobby Coach supports writing/reading practice.
