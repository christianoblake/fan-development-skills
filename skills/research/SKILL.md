---
name: research
description: Proposes and scores candidate audience segments from an operator's description of their business, using an 8-dimension diagnosis weighted per-business rather than a fixed rubric — and states the reasoning behind that weighting before scoring runs. Actually searches the web when a search capability is available, both to help describe an unfamiliar company and to source evidence for scoring; asks the operator to paste material when it isn't. Reads using-fan-development-skills first for the toolkit's operating behaviors and mode detection. Use when an operator doesn't know which audience segment to prioritize, wants to pressure-test a segment they already believe in, or is starting the fan-development-skills flow from scratch.
---

# Research

## Overview

`research` is the diagnostic entry point for this toolkit. Given a description
of a business and its audience, it proposes candidate segments, scores them on
eight dimensions, and recommends which funnel stage — awareness, engagement,
or integration — is the actual bottleneck for the top segment. Everything else
in this toolkit either consumes that diagnosis (the router's Full-Flow Mode)
or exists to pressure-test one segment on its own (thought-partner mode).

## When to Use

- An operator doesn't know which segment to prioritize and wants a
  from-scratch diagnosis.
- An operator already has a segment in mind and wants it pressure-tested, not
  just validated.
- Run automatically first, always, in the router's Full-Flow Mode — its output
  is the weighting input for `awareness`, `engagement`, and `integration`.
- **Not for** refining an already-agreed single-stage program with no segment
  question attached — go directly to `awareness`, `engagement`, or
  `integration` for that.

## Read First

Before anything else, read and apply
`using-fan-development-skills/SKILL.md` — it defines the Core Operating
Behaviors, detects Single-Skill vs. Full-Flow Mode, and defines Session
Continuity & File Output. Check for an existing `research.md` for this
business before proceeding, and read it in as context if one exists.
Everything below assumes those behaviors are already active.

## Resolve the Intake

Two things get resolved before any proposing or scoring happens.

**1. Mode.**
- **Build-from-scratch** — the operator doesn't have a segment yet, or wants
  a full diagnosis from zero.
- **Thought-partner/refine** — the operator already has a segment or
  in-flight program and wants it pressure-tested. Skip Propose Candidates
  below; score only the segment(s) they name.

**2. Starting point**, regardless of mode — what the operator has to work
from:
- **Share data** — they paste or describe real data about their audience.
- **Identify softening** — they name where a metric is declining.
- **Name a target metric** — they state what they want to move, with no
  current baseline.

**Build-from-scratch only — establish what the business is:**
1. Ask for the company or product name.
2. Ask whether to research it (search the web to draft a description) or take
   the operator's own description instead.
3. If web-researched: draft the description, show it back, and confirm it's
   accurate before continuing. Do not proceed on an unconfirmed description.
4. If operator-provided: use it as given — it's already theirs, no
   confirmation loop needed.

## Propose Candidates (build-from-scratch mode only)

1. Start from the default list: new/first-touch users, lapsed users, power
   users not yet advocates, adjacent-market prospects, internal/employee
   advocates. This list is a floor, never a ceiling.
2. Add candidates the business/audience description or shared data actually
   suggests. A run that scores only the five defaults, unmodified, regardless
   of what business it's given is a bug, not a valid outcome — pressure
   yourself to find at least one segment specific to what the operator
   described.

## Source Discernment

Before searching or asking for material, reason out loud about what kind of
external evidence actually matters for this business — a consumer app implies
app-store reviews and social listening; a B2B/enterprise product implies
analyst reports and community benchmarks; a local/physical business implies
local market data. State this reasoning; never apply a fixed hierarchy
regardless of business type.

## Search or Ask

If a web search or fetch capability is available in this session, use it —
both to fill in the business description above and to source real evidence
for scoring below. This is the default path, not a hypothetical to describe
and then skip. If no such capability is available, say so plainly and ask the
operator to paste source material instead — see Graceful Degradation.

## Weight the Dimensions

The eight dimensions — strategic fit, evidence of affinity, segment size,
conversion likelihood, repeat/retention potential, ease of activation,
operational feasibility, evidence confidence — are never weighted the same
way twice. Before scoring:

1. State a summary of the business/audience understanding built so far.
2. Propose a specific weighting — which dimensions matter more for this
   business and why — with the reasoning tied to that context.
3. Pose it back to the operator as a question, guess attached — summary, then a
   question, then a guess for how they'd weight it based on the context
   built so far.
4. Wait for their reaction before scoring. Fold in any correction.

## Score

Score every candidate segment (defaults plus additions, or the named
segment(s) in thought-partner mode) against the weighted dimensions. Any
claim without solid evidence — a size estimate, a conversion assumption, a
"this segment behaves like X" comparison — gets `LOW_EVIDENCE` explicitly,
not smoothed into a confident-sounding number.

## Graceful Degradation

No search capability, or a search that comes back thin: ask the operator to
paste source material directly rather than inventing evidence to fill the
gap. This is a first-class fallback, not an edge case — state plainly when
it's happening, don't silently degrade quality without saying so.

## Output the Brief

- Ranked candidate segments — or, in thought-partner mode, the named
  segment's score with a note on how it compares to what a from-scratch scan
  would likely surface.
- Evidence per dimension, with `LOW_EVIDENCE` flags visible, not buried in
  prose.
- A recommended stage emphasis for the top segment(s) — is the bottleneck
  awareness, engagement, or integration? This becomes the weighting input if
  the operator continues into the full flow.
- Close per Mode Detection in the router: Single-Skill Mode ends with a
  stated next-step recommendation; the Full-Flow check-in stop is the
  router's job, not this skill's.
- Save to `fan-development/<business-slug>/research.md` per the router's
  Session Continuity & File Output, and state the path in the close.

## Common Rationalizations

| Rationalization | Reality |
|---|---|
| "I already searched the web for the description, no need to also confirm it with the operator." | Searching and confirming aren't substitutes for each other. Draft it from the search, then still show it back — the operator catches a wrong assumption in five seconds; you won't catch your own. |
| "The default five segments already cover this business well enough." | That's the outcome to distrust most. If every run lands on the same five, the diagnosis isn't adapting to what's actually described — go back and look for what's specific to this business. |
| "Equal weights across all 8 dimensions is safer than committing to a business-specific rationale." | Equal weighting is itself a claim — that all eight matter the same for this business — and it's usually wrong. State the real reasoning and let the operator correct it if it's off. |
| "The operator clearly wants me to validate the segment they already named." | Pressure-testing means it might not survive. Score it honestly — confirming a bad bet a week before budget commits is worse than telling them now. |
| "Search came back thin, I'll fill the gaps with reasonable industry assumptions." | That's inventing evidence. Say the search came back thin and ask for pasted material — don't let a weak result quietly become a confident-sounding claim. |

## Red Flags

- Every run proposing the same five default segments with no business-specific
  additions.
- Weighting applied without ever stating the reasoning behind it, or applied
  identically across unrelated business types.
- A `LOW_EVIDENCE`-worthy claim presented without the flag.
- A web-researched business description used without ever being shown back
  for confirmation.
- Thought-partner mode running a full candidate-proposal sweep the operator
  didn't ask for.
- A search capability available in the session but never actually invoked.

## Verification

Before treating a run as complete, confirm:

- [ ] Mode (build-from-scratch vs. thought-partner) and starting point were
      resolved before any proposing or scoring
- [ ] Build-from-scratch: the business description is either operator-provided
      or web-researched-and-confirmed before continuing
- [ ] At least one candidate segment beyond the default five, when the
      business description supports one
- [ ] Source-discernment reasoning was stated out loud, not applied as a
      fixed hierarchy
- [ ] A web search capability was actually invoked when available in the
      session
- [ ] Dimension weighting was reasoned per-business and confirmed with the
      operator via the summary/question/guess pattern before scoring
- [ ] Every `LOW_EVIDENCE`-worthy claim is flagged, not smoothed over
- [ ] Output includes ranked segments (or the thought-partner score),
      evidence, confidence flags, and a stage-emphasis recommendation
- [ ] An existing `research.md` for this business was checked for and read
      first if one existed; the brief was saved to the correct path per
      Session Continuity & File Output
