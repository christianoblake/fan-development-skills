---
name: integration
description: Designs how casual engagement with a named audience segment becomes an identified, ongoing relationship — a membership, champion, or pathway mechanic — and ties that relationship explicitly to a business outcome. Reads using-fan-development-skills first for the toolkit's operating behaviors and mode detection. Use when the segment engages once but doesn't return, or can't be identified the second time — whether arriving from a research diagnosis, chained in the full flow, or invoked directly on a segment the operator already has in mind.
---

# Integration

## Overview

`integration` answers one question for a named segment: how does a casual,
anonymous interaction become an identified, ongoing relationship — and what
business outcome does that relationship actually connect to?

## When to Use

- The segment engages casually but doesn't return, or can't be identified or
  tracked the second time — that's the bottleneck.
- Arriving from a `research` diagnosis (full-flow or a prior standalone run)
  that named integration as the bottleneck.
- Invoked directly on a segment the operator already has in mind.
- **Not for** a segment that hasn't engaged at all yet — that's `awareness`
  or `engagement`, depending on which gap comes first.

## Read First

Before anything else, read and apply
`using-fan-development-skills/SKILL.md` — it defines the Core Operating
Behaviors, detects Single-Skill vs. Full-Flow Mode, and defines Session
Continuity & File Output. Check for an existing business-level `research.md`
and, once the segment is established, this segment's own `integration.md`
(and any `integration-*.md` options) before proceeding, and read in whatever
exists. Everything below assumes those behaviors are already active.

## Resolve the Intake

1. **Establish the segment.** If a segment or audience hasn't been named yet
   — this skill invoked cold — ask which one to focus on. If the operator
   doesn't know, mention that `research` would diagnose this first, but
   don't force it; proceed with whatever segment they name directly.
2. **Mode.**
   - **Build mode** — designing an integration pathway fresh for this
     segment.
   - **Thought-partner/refine mode** — an integration pathway already exists
     for this segment and the operator wants it refined or pressure-tested,
     not designed from scratch. Capture what already exists and the specific
     refinement question instead of starting from zero.
3. **Ground the brief.** Ask for any metrics, resource considerations, or
   priorities that would shape the recommendation. Missing answers don't
   block the brief — flag the gap and proceed with what's known.

## Design the Pathway

1. Identify the mechanic that turns a casual, anonymous interaction into an
   identified one — a membership, a champion tier, a pathway with a clear
   next step — appropriate to what's been shared about this segment and the
   business.
2. If a search capability is available, use it to ground the mechanic choice
   in real information about comparable pathway or membership models for
   this kind of segment or business. A mechanic proposed with no basis is
   exactly what `LOW_EVIDENCE` flagging exists to catch.
3. State explicitly how the identified relationship connects to a business
   outcome — not "more loyalty," a named outcome: retention, referral,
   revenue, advocacy, or whatever's real for this business.

## Output the Brief

Assemble: the situation (why engagement is staying casual/anonymous), the
recommended approach with reasoning (the pathway mechanic and the business
outcome it connects to), the resourcing implication, the outcome metric to
defend (per the router's Core Operating Behavior #4 — something that
reflects the relationship actually becoming identified, like tracked repeat
engagement or conversion into the pathway, stated plainly, not raw repeat
visits), risks or watch-outs, and a check-in question
posed back to the operator. Close per the router's Mode Detection:
Single-Skill Mode ends with a stated next-step recommendation; the Full-Flow
check-in stop is the router's job, not this skill's. Save per the router's
Session Continuity & File Output — the canonical
`fan-development/<business-slug>/<segment-slug>/integration.md` for a
refinement, or a distinctly-slugged option file when the operator asked for
alternatives — and state the path in the close.

## Common Rationalizations

| Rationalization | Reality |
|---|---|
| "A loyalty or membership program is the obvious answer regardless of what this segment or business actually needs." | "Obvious" is the same trap as elsewhere — ground the specific mechanic in what's been shared, or flag the gap. |
| "A repeat-visit count on its own is a fine metric." | Repeat visits without identification isn't integration. The metric needs to reflect that the relationship is now identified or trackable, not just that activity happened twice. |
| "The business outcome this connects to is self-evident, no need to state it." | State it anyway — the explicit business-outcome connection is the discipline this skill exists to enforce, not an implied one. |
| "This is a refinement request, I can skip straight to a tweak without confirming what's already there." | Thought-partner mode still needs to capture what exists before refining it — confirm the current pathway before recommending a change to it. |

## Red Flags

- A pathway or membership mechanic proposed with no stated business-outcome
  connection.
- A metric measuring repeat activity without measuring identification.
- A mechanic that doesn't reference anything shared about the segment or
  business — generic loyalty-program boilerplate.
- Missing resourcing or priority context never asked for.

## Verification

Before treating a run as complete, confirm:

- [ ] The segment was established before any design began — asked for, or
      already provided
- [ ] Mode (build vs. thought-partner) was resolved and respected
- [ ] The pathway mechanic is tied explicitly to a named business outcome
- [ ] Search was used to ground the mechanic choice when available;
      `LOW_EVIDENCE` flagged when it wasn't
- [ ] The brief includes situation, approach with reasoning, resourcing, an
      outcome metric, risks, and a check-in question
- [ ] Missing context was asked for explicitly and/or flagged as a gap, not
      silently assumed
- [ ] Existing files (business-level `research.md`, this segment's
      `integration.md`/option files) were checked for and read first; the
      brief was saved to the correct path per Session Continuity & File
      Output
