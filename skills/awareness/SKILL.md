---
name: awareness
description: Diagnoses how a named audience segment currently discovers this product or business, names the specific discovery gap, and recommends the channel and message that closes it — grounded in real information about the segment when a search capability is available, LOW_EVIDENCE-flagged when it isn't. Reads using-fan-development-skills first for the toolkit's operating behaviors and mode detection. Use when the bottleneck is that people who'd care about this segment don't know it exists yet — whether arriving from a research diagnosis, chained in the full flow, or invoked directly on a segment the operator already has in mind.
---

# Awareness

## Overview

`awareness` answers one question for a named segment: how does discovery
actually break down for them right now, and what closes it? Not "more
awareness" in the abstract — the specific point where a segment that would
plausibly care never encounters the product or business at all.

## When to Use

- People who'd care about this segment don't know the product/business
  exists — that's the specific bottleneck this skill addresses.
- Arriving from a `research` diagnosis (full-flow or a prior standalone run)
  that named awareness as the bottleneck.
- Invoked directly on a segment the operator already has in mind, with or
  without a research diagnosis behind it.
- **Not for** a segment that already knows about the product but hasn't
  taken a first step — that's `engagement`.

## Read First

Before anything else, read and apply
`using-fan-development-skills/SKILL.md` — it defines the Core Operating
Behaviors, detects Single-Skill vs. Full-Flow Mode, and defines Session
Continuity & File Output. Check for an existing business-level `research.md`
and, once the segment is established, this segment's own `awareness.md` (and
any `awareness-*.md` options) before proceeding, and read in whatever exists.
Everything below assumes those behaviors are already active.

## Resolve the Intake

1. **Establish the segment.** If a segment or audience hasn't been named yet
   — this skill invoked cold — ask which one to focus on. If the operator
   doesn't know, mention that `research` would diagnose this first, but
   don't force it; proceed with whatever segment they name directly.
2. **Mode.**
   - **Build mode** — designing an awareness approach fresh for this
     segment.
   - **Thought-partner/refine mode** — an awareness program already exists
     for this segment and the operator wants it refined or pressure-tested,
     not designed from scratch. Capture what already exists and the specific
     refinement question instead of starting from zero.
3. **Ground the brief.** Ask for any metrics, resource considerations, or
   priorities that would shape the recommendation. Missing answers don't
   block the brief — flag the gap and proceed with what's known.

## Diagnose the Discovery Gap

1. Reason out how this segment most plausibly encounters — or fails to
   encounter — the product or business today, given what's been shared
   about them.
2. If a search capability is available, use it to ground this in real
   information about the segment or comparable programs. A channel
   recommendation with no basis beyond a guess is exactly what `LOW_EVIDENCE`
   flagging exists to catch.
3. Name the specific gap — not "more awareness," but the point where this
   segment's actual discovery path breaks down.

## Recommend Channel and Message

- The channel(s) that actually reach this segment where they already are,
  not a generic list.
- The message framing that closes the specific gap named above, not a
  generic pitch.
- State the reasoning behind the recommendation, not just the
  recommendation.

## Output the Brief

Assemble: the situation (the discovery gap as diagnosed), the recommended
approach with reasoning (channel plus message), the resourcing implication,
the outcome metric to defend (per the router's Core Operating Behavior #4 —
something tied to an outcome, like a qualified first contact, stated
plainly), risks or watch-outs, and a
check-in question posed back to the operator. Close per the router's Mode
Detection: Single-Skill Mode ends with a stated next-step recommendation; the
Full-Flow check-in stop is the router's job, not this skill's. Save per the
router's Session Continuity & File Output — the canonical
`fan-development/<business-slug>/<segment-slug>/awareness.md` for a
refinement, or a distinctly-slugged option file when the operator asked for
alternatives — and state the path in the close.

## Common Rationalizations

| Rationalization | Reality |
|---|---|
| "This segment obviously uses [channel], I don't need to check." | "Obviously" is exactly the assumption Core Operating Behavior #1 exists to catch — ground it or flag it. |
| "The operator named the segment, that's enough context to design the whole recommendation." | Naming a segment isn't the same as sharing what would shape the recommendation — ask for resourcing and priorities before finalizing. |
| "A reach or impressions number is an easy metric to hand back." | It's also a vanity metric. Name what happens after the impression — a qualified first contact, a completed action — not the impression itself. |
| "This is a refinement request, I can skip straight to a tweak without confirming what's already there." | Thought-partner mode still needs to capture what exists before refining it — confirm the current approach before recommending a change to it. |

## Red Flags

- A channel or message recommendation with no stated reasoning behind it.
- A claim about how the segment behaves with no `LOW_EVIDENCE` flag and no
  source backing it.
- A metric that's an activity or vanity count rather than an outcome.
- Thought-partner mode producing a from-scratch design instead of a
  refinement.
- A brief produced without ever asking for resourcing or priority context.

## Verification

Before treating a run as complete, confirm:

- [ ] The segment was established before any diagnosis began — asked for, or
      already provided
- [ ] Mode (build vs. thought-partner) was resolved and respected
- [ ] The discovery gap is named specifically, not just "more awareness
      needed"
- [ ] Search was used to ground the channel/message recommendation when
      available; `LOW_EVIDENCE` flagged when it wasn't
- [ ] The brief includes situation, approach with reasoning, resourcing, an
      outcome metric, risks, and a check-in question
- [ ] Missing context was asked for explicitly and/or flagged as a gap, not
      silently assumed
- [ ] Existing files (business-level `research.md`, this segment's
      `awareness.md`/option files) were checked for and read first; the brief
      was saved to the correct path per Session Continuity & File Output
