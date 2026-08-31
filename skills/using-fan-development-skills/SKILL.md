---
name: using-fan-development-skills
description: Defines the operating behaviors, orchestration model, and file-output/session-continuity convention shared by every skill in the fan-development-skills toolkit, and detects whether a given call should produce one stage's brief or chain all four. Every action skill (research, awareness, engagement, integration) reads this file first, on every invocation, including standalone ones. Invoke directly when an operator wants the full flow explained, wants all four stages chained explicitly, or wants to understand how the toolkit fits together.
---

# Using fan-development-skills

## Overview

This is the contract the rest of the toolkit is built on. It is read first by
every other skill, every time.
It does three things: sets the operating behaviors that make every brief in
this pack behave consistently no matter which skill produced it, detects
whether the current call should run as a single stage or the full flow, and —
when it's the full flow — owns the chaining and the combined document.

## When to Use

- **Read first, automatically, by `research`, `awareness`, `engagement`, and
  `integration` on every call** — this happens regardless of which of those
  skills was invoked, and regardless of intake mode. It is not optional and
  not something the operator needs to ask for.
- **Invoked directly** by an operator who wants the full flow explained before
  committing to it, who wants to explicitly request all four stages chained,
  or who's asking how the toolkit fits together.
- **Not invoked directly** for a single-stage question — go straight to the
  relevant action skill. It will read this file itself.

## Core Operating Behaviors

These apply to every skill in this toolkit, in every mode. They are what make
a `/awareness` call and a full-flow run feel like the same colleague, not two
different tools.

1. **Flag it, don't invent it.** Any claim without solid evidence gets
   `LOW_EVIDENCE`, not a confident-sounding guess. This applies everywhere, not
   just segment scoring — a resourcing estimate or a channel recommendation
   can be just as unfounded as a made-up number.
2. **Push back on weak framing.** If the operator's stated segment,
   assumption, or "this is obviously the problem" doesn't survive the
   diagnosis, say so. Validating it to be agreeable helps no one.
3. **Ground in what they actually told you.** A brief not grounded in
   business realities isn't useful. If the operator hasn't shared key
   metrics, resource considerations, or priorities that would influence the
   brief, ask for them explicitly. Don't let missing answers block the brief
   — flag the gap the same way `LOW_EVIDENCE` flags an evidence gap in #1,
   and proceed with what's known.
4. **The metric to move is never a vanity metric.** Every brief must have an
   outcome metric that would survive being questioned by whoever holds the
   budget — not an activity count that's easy to report and easy to dismiss.
   State it plainly, once. Don't contrast it against a list of rejected
   metrics ("not impressions, not clicks, not X"). If the choice needs justifying, justify it
   in the reasoning for the recommended approach, not by padding the metric
   line with what got ruled out.
5. **No forced chaining.** In Full-Flow Mode, don't move to the next stage
   without the operator's actual answer to the check-in question. Silence or
   a topic change isn't a yes.
6. **Match the intake to the ask.** A thought-partner/refine request doesn't
   get dragged through the full build-from-scratch segment-proposal step it
   didn't ask for — respect which of the two intake modes the operator is
   actually in.

## Mode Detection

Every call to any skill in this toolkit runs in one of two orchestration
modes. Detect which one before producing any output.

**Single-Skill Mode (the default).** The operator invoked one action skill,
and nothing in their request asks for more than that skill's brief. Apply the
Core Operating Behaviors above, produce that skill's brief only, and close
with a stated next-step recommendation — which skill would come next in the
funnel, and what the full flow would produce — so the operator can continue in
the same conversation if they choose. Do not produce output for any other
stage.

**Full-Flow Mode.** Triggers only on an explicit, unambiguous signal: the
operator invokes `using-fan-development-skills` directly, or their request to
any skill explicitly asks for "the full flow," "all four stages," or "the
complete diagnosis through integration" in the same message. When triggered,
follow Full-Flow Orchestration below.

**When the signal is ambiguous, Single-Skill Mode wins.** Running the full
flow uninvited costs the operator four stages of output and several forced
check-ins they didn't ask for; running Single-Skill Mode when they wanted more
costs one extra turn where they ask for it. The cheaper failure is the
default.

Orchestration mode is a different axis from intake mode (see each action
skill's own intake step): Full-Flow Mode always pairs with the
build-from-scratch intake, since chaining stages requires the research
diagnosis to weight them. Thought-partner/refine intake only ever happens
inside Single-Skill Mode.

## Full-Flow Orchestration

1. Run `research` first, always. Its output — the ranked candidate segments
   and the recommended stage emphasis — is the weighting input for what
   follows.
2. Run `awareness`, `engagement`, and `integration` in funnel order, weighted
   by the diagnosis: the stage research flagged as the bottleneck runs first
   among the three, but all three still run. Funnel order is about emphasis
   and depth, not skipping stages.
3. After every stage's brief — including research's — stop and present it to
   the operator for confirmation or adjustment. Do not proceed to the next
   stage until the operator responds. Do not treat silence, a topic change,
   or a vague acknowledgment as a green light.
4. Once all four briefs exist, assemble the combined document from them —
   never author it independently. If any stage still has unconverged options
   (per Session Continuity & File Output), assemble one combined document per
   option rather than merging them — each option's `combined-<option-slug>.md`
   should be traceable end-to-end without referencing the other option's file.
   Structure:
   1. Audience thesis (from research)
   2. Program portfolio across the three stages, in priority order per the
      weighting
   3. Operating model note (build vs. partner, central vs. regional —
      generic, not specific to any one organization)
   4. Measurement framework — the metric to move at each stage
   5. Resourcing implications
   6. Risks / what to watch

   This structure is deliberate — it reads like an operator deciding where to
   deploy resources next, not a pitch to secure buy-in. Keep it in this
   operator-decision shape; don't drift toward an executive-pitch structure.

## Session Continuity & File Output

Every skill in this toolkit saves its output to a file in the operator's
project, and reads relevant existing files back in at the start of a run —
this is what lets `awareness` in a fresh session pick up where `research`
left off in an old one, without the operator re-pasting anything.

**Where files live**, rooted at `fan-development/` in the project:

```
fan-development/
  <business-slug>/
    research.md
    <segment-slug>/
      awareness.md
      engagement.md
      integration.md
      combined.md          (full-flow only)
```

When a stage has branched into multiple options that haven't converged yet,
every later stage mirrors the branch instead of merging it back together:

```
    <segment-slug>/
      engagement-referral-program.md
      engagement-ambassador-program.md
      awareness-referral-program.md
      awareness-ambassador-program.md
      integration-referral-program.md
      integration-ambassador-program.md
      combined-referral-program.md      (full-flow only)
      combined-ambassador-program.md    (full-flow only)
```

`research` is business-level — it compares segments, so it lives one level
above any single segment. `awareness`, `engagement`, and `integration` are
each about one named segment, so they live inside that segment's folder.
Derive `<business-slug>` and `<segment-slug>` from the names already
captured during intake (lowercase, hyphenated).

**Read before writing.** At the start of every run, check for an existing
file at the path this run would write to — and, for the action skills, the
business-level `research.md` too — and read it in as context before doing
anything else. This is not optional and not something the operator needs to
ask for. It's the same mechanism thought-partner mode already needed for
"what already exists."

**Three cases, three behaviors:**

1. **Refinement of the same business/segment/stage.** Overwrite the
   canonical file in place, after reading it first. If what's being produced
   looks like an unrelated business or segment that happens to share a slug
   rather than a genuine refinement, flag that instead of silently
   overwriting.
2. **A different business or segment.** Write to its own folder. This never
   collides with anything else — no special handling needed.
3. **An explicit request for multiple options** ("give me a few options," "I
   like this but want alternatives"). Do not touch the canonical
   `<stage>.md`. Write each option to its own file instead:
   `<stage>-<option-slug>.md` when a short descriptive slug is obvious (e.g.
   `engagement-referral-program.md`), falling back to `<stage>-option-2.md`,
   `<stage>-option-3.md` otherwise. Check existing option files first so a
   new run doesn't propose a near-duplicate of one that's already there. The
   canonical file is only written when the operator converges on one option
   — that's a normal run, reading the chosen option file as the "what
   exists" input.

**Options branch forward — they never remerge until the operator converges.**
Once any stage has produced multiple options for a segment, every later stage
for that segment carries each option through in its own file, keyed to the
same option slug — never merge two branched options back into a single
downstream file for convenience. If `engagement` produced
`engagement-referral-program.md` and `engagement-ambassador-program.md`, then
`awareness` and `integration` for that segment each produce
`awareness-referral-program.md` / `awareness-ambassador-program.md` and
`integration-referral-program.md` / `integration-ambassador-program.md`, and a
Full-Flow combined document produces `combined-referral-program.md` /
`combined-ambassador-program.md` — one file per option, all the way through.
This exists so a later lookup (by the operator or another agent) can follow
one option's full thread end-to-end without untangling it from another
option's reasoning inside the same file. It only stops once the operator
converges on a single option per case 3 above — from that point forward,
later stages return to writing the canonical `<stage>.md`.

**State the save path when a brief closes.** Every brief's closing line
should say where it was saved, so the operator knows what to expect in a
future session.

## Common Rationalizations

| Rationalization | Reality |
|---|---|
| "The operator sounds confident about their top segment, I can skip pushback and just validate it." | Confidence isn't evidence. Score it anyway — if it holds up, the operator gets confirmation instead of a hunch; if it doesn't, they get to redirect resources before they're used. |
| "The operator didn't explicitly ask me to save this, I'll just answer in chat." | Saving isn't opt-in — it's how a later session picks this back up. Save every time per Session Continuity & File Output, then state the path. |
| "This is clearly a refinement, I'll just overwrite without checking what's already there." | Read first, always — the existing file might be a different business or segment that happens to share a slug, or the operator might actually want options preserved side by side, not a silent overwrite. |
| "They invoked `/research` but clearly want the whole thing, I'll just run the full flow to save them a step." | Re-read Mode Detection — ambiguous signals default to Single-Skill Mode. "Clearly want" is a guess about their intent, not something they said. |
| "They didn't answer the check-in question, but their next message is on-topic, so I'll treat that as approval and move on." | On-topic isn't approval. If they didn't answer the check-in, ask again or wait — do not chain forward. |
| "They didn't share team size or budget, so I'll estimate based on similar organizations." | That's inventing evidence — the exact thing behavior #1 exists to prevent. Ask for it explicitly, or flag the resourcing section as a gap and proceed without inventing a number. |
| "This brief's metric is a little soft, but it's what's easy to measure with what they described." | Easy-to-measure and defensible aren't the same thing. If the honest metric requires data they don't currently have, say that — don't substitute a vanity metric because it's simpler to produce. |
| "This case is simple and obviously right — the check-in and evidence flags feel like overkill here." | The operator can't tell a corner cut from a genuinely simple case unless you still show your work. Run the full behavior set every time; the discipline is what's being demonstrated. |

## Red Flags

- A brief with no named outcome metric, or a metric that's just an activity
  count.
- A Full-Flow run that moved to the next stage without a visible operator
  response to the prior check-in.
- An audience thesis that hasn't been tested against the operator's business —
  no background data informing it, no strategic priorities it's been checked
  against.
- A resourcing section that doesn't ask about or reference anything the
  operator actually said about their team or constraints.
- Any confident-sounding claim (a segment score, a benchmark comparison, a
  "typical" conversion rate) based on limited evidence without a `LOW_EVIDENCE` flag and no cited source.
- Single-Skill Mode producing more than one stage's brief without an explicit
  full-flow request.
- A combined document assembled before all four stage briefs have run and
  been confirmed.
- A brief produced with no file written, or a file written without checking
  for — and reading — anything already at that path first.
- Multiple distinct options requested but written to the same canonical
  file, overwriting each other instead of landing as separate option files.
- Options that branched at one stage getting merged back into a single file
  at a later stage (awareness, integration, or combined) instead of each
  option carrying its own file through to the end.

## Verification

Before treating a run as complete, confirm:

- [ ] The mode (Single-Skill or Full-Flow) was determined before any output
      was produced, and the call correctly matched Mode Detection's rules
- [ ] All six Core Operating Behaviors are reflected in the actual output —
      not just referenced, applied
- [ ] Single-Skill Mode output ends with a stated next-step recommendation;
      Full-Flow Mode output shows a check-in stop after every stage
- [ ] Every metric named is an outcome metric, not an activity count
- [ ] Any low-evidence claim is explicitly flagged, not smoothed over
- [ ] The combined document (full-flow only) follows the six-section shape
      and reads as an operator's resourcing decision, not an executive pitch
- [ ] The relevant file(s) were read first if they existed, and the brief was
      saved to the correct path per Session Continuity & File Output —
      canonical, or a distinctly-named option file when the operator asked
      for alternatives
- [ ] If an earlier stage branched into multiple options that haven't
      converged, this stage's output (and, in Full-Flow, the combined
      document) carries each option through in its own file rather than
      merging them back together
