---
name: engagement
description: Designs a low-barrier engagement mechanic for a named audience segment, built around a format the segment is already comfortable with elsewhere rather than one invented from scratch — grounded in real information about the segment when a search capability is available. Reads using-fan-development-skills first for the toolkit's operating behaviors and mode detection. Use when the segment already knows the product/business exists but hasn't taken a first real step — whether arriving from a research diagnosis, chained in the full flow, or invoked directly on a segment the operator already has in mind.
---

# Engagement

## Overview

`engagement` answers one question for a named segment: what's the
lowest-barrier way to get them to take a first real step, using a format
they're already comfortable with somewhere else rather than one invented for
this occasion?

## When to Use

- The segment knows the product or business exists but hasn't engaged —
  that's the bottleneck.
- Arriving from a `research` diagnosis (full-flow or a prior standalone run)
  that named engagement as the bottleneck.
- Invoked directly on a segment the operator already has in mind.
- **Not for** a segment that doesn't know the product exists yet — that's
  `awareness`. **Not for** a segment that already engages casually but never
  becomes identified or repeat — that's `integration`.

## Read First

Before anything else, read and apply
`using-fan-development-skills/SKILL.md` — it defines the Core Operating
Behaviors, detects Single-Skill vs. Full-Flow Mode, and defines Session
Continuity & File Output. Check for an existing business-level `research.md`
and, once the segment is established, this segment's own `engagement.md` (and
any `engagement-*.md` options) before proceeding, and read in whatever
exists. Everything below assumes those behaviors are already active.

## Resolve the Intake

1. **Establish the segment.** If a segment or audience hasn't been named yet
   — this skill invoked cold — ask which one to focus on. If the operator
   doesn't know, mention that `research` would diagnose this first, but
   don't force it; proceed with whatever segment they name directly.
2. **Mode.**
   - **Build mode** — designing an engagement mechanic fresh for this
     segment.
   - **Thought-partner/refine mode** — an engagement mechanic already exists
     for this segment and the operator wants it refined or pressure-tested,
     not designed from scratch. Capture what already exists and the specific
     refinement question instead of starting from zero.
3. **Ground the brief.** Ask for any metrics, resource considerations, or
   priorities that would shape the recommendation. Missing answers don't
   block the brief — flag the gap and proceed with what's known.

## Design the Mechanic

1. Identify a format this segment is already comfortable with elsewhere —
   not a format invented for this program. Reason out what that format
   actually is, given what's been shared about the segment.
2. If a search capability is available, use it to ground the format choice
   in real information about how this segment engages elsewhere. A mechanic
   invented with no basis is exactly what `LOW_EVIDENCE` flagging exists to
   catch.
3. Design the mechanic for the lowest realistic barrier to a first step —
   not the most ambitious version, the one most likely to actually get
   taken.

## Output the Brief

Assemble: the situation (why this segment hasn't engaged yet), the
recommended approach with reasoning (the mechanic and why this format), the
resourcing implication, the outcome metric to defend (per the router's Core
Operating Behavior #4 — something that reflects a completed first step, not
raw participation, stated plainly), risks or watch-outs, and a
check-in question posed back to the operator. Close per the router's Mode
Detection: Single-Skill Mode ends with a stated next-step recommendation; the
Full-Flow check-in stop is the router's job, not this skill's. Save per the
router's Session Continuity & File Output — the canonical
`fan-development/<business-slug>/<segment-slug>/engagement.md` for a
refinement, or a distinctly-slugged option file when the operator asked for
alternatives — and state the path in the close.

## Common Rationalizations

| Rationalization | Reality |
|---|---|
| "A more ambitious activation is more exciting than this segment's existing habits, let's design something new." | Novelty isn't the goal — barrier-to-first-step is. If it's not a format they're already comfortable with, the barrier just went up, not down. |
| "A participation count is a clean number to report." | It's also a vanity metric if it doesn't distinguish a real first step from a passive view. Name the outcome, not the count. |
| "This mechanic is obviously going to work for this segment." | "Obviously" is the assumption Core Operating Behavior #1 exists to catch — ground it or flag it. |
| "This is a refinement request, I can skip straight to a tweak without confirming what's already there." | Thought-partner mode still needs to capture what exists before refining it — confirm the current mechanic before recommending a change to it. |

## Red Flags

- A mechanic invented without reference to a format the segment already uses
  elsewhere.
- No stated barrier-to-entry reasoning — why this is the low-barrier version,
  not just a version.
- A vanity metric standing in for an outcome metric.
- Missing resourcing or priority context never asked for.

## Verification

Before treating a run as complete, confirm:

- [ ] The segment was established before any design began — asked for, or
      already provided
- [ ] Mode (build vs. thought-partner) was resolved and respected
- [ ] The mechanic is built around a format the segment already uses
      elsewhere, not an invented one
- [ ] Search was used to ground the format choice when available;
      `LOW_EVIDENCE` flagged when it wasn't
- [ ] The brief includes situation, approach with reasoning, resourcing, an
      outcome metric, risks, and a check-in question
- [ ] Missing context was asked for explicitly and/or flagged as a gap, not
      silently assumed
- [ ] Existing files (business-level `research.md`, this segment's
      `engagement.md`/option files) were checked for and read first; the
      brief was saved to the correct path per Session Continuity & File
      Output
