# fan-development-skills

**A full-funnel, diagnostic-first Claude skills toolkit for anyone trying to grow an audience.**

You describe your business and your audience `/research` proposes and scores
candidate segments and tells you where the bottleneck is: awareness, engagement, or integration. From there, three action
skills turn that diagnosis into a plan, one stage at a time, with you in the loop
after each one.

```
                         ┌─ research diagnosis ─┐
                         │  candidate segments  │
                         │  scored on 8 dims    │
                         │  stage-emphasis call │
                         └───────────┬──────────┘
                                     │
                      ┌──────────────┼──────────────┐
                      ▼              ▼              ▼
                 awareness      engagement      integration
              discovery gap   low-barrier      identified,
              channel + msg    mechanic        ongoing
                                design         relationship
                      │              │              │
                      └──────────────┼──────────────┘
                                     ▼
                          one combined document:
                     audience thesis → program portfolio →
                    operating model → measurement → resourcing
```

Each stage is also a standalone thought-partner. For example, f you're already running
an engagement program and just want a second opinion, use `/engagement` on its
own.

## What's in here

| Skill | What it does | Use when | Key principle |
|---|---|---|---|
| [`using-fan-development-skills`](skills/using-fan-development-skills/SKILL.md) | Router. Defines the operating rules every other skill follows, and decides single-skill vs. full-flow mode. | If you're not sure where to start this is the spot. | Same rules, each time |
| [`research`](skills/research/SKILL.md) | Proposes and scores candidate audience segments from your own description of your business and audience. Flags weak evidence instead of guessing. | You don't know which segment to prioritize, or you want to pressure-test the one you already believe in. | Flag the gap, don't guess |
| [`awareness`](skills/awareness/SKILL.md) | How a segment currently discovers you, where that discovery breaks down, and what channel/message closes the gap. | The bottleneck is that people who'd care don't know you exist. | Known isn't found |
| [`engagement`](skills/engagement/SKILL.md) | A low-barrier engagement mechanic, designed around a format the segment is already comfortable with elsewhere. | People know you exist but haven't taken a first real step. | Meet them on their terms |
| [`integration`](skills/integration/SKILL.md) | How casual engagement becomes an identified, ongoing relationship — and how that connects to a business outcome. | People engage once and don't come back, or you can't tell who they are the second time. | Casual isn't counted |

Every skill produces a structured brief: the situation, the recommended approach
and why, the resourcing implication, the metric to track for that stage, risks to watch, and a check-in question back to you. Full-flow runs
assemble all four briefs into one document, in an order weighted by the diagnosis.

## Quick start

**Clone the repo:** download the skills to your computer.
```bash
git clone https://github.com/varianthuman7-ops/fan-development-skills.git
```

**Claude Code:** copy `skills/*` into your project's `.claude/skills/` (or
`~/.claude/skills/` to make them available everywhere), then run:

```
/using-fan-development-skills
```

**Claude.ai:** zip a skill folder and upload it under Settings → Capabilities →
Skills.

Either way, `/using-fan-development-skills` is the natural starting point for a build-from-scratch
diagnosis and overview of the toolkit. If you already know which stage you want help with, invoke that skill
directly — see the table above.

## How it's built

Five skill folders, one `SKILL.md` each, no shared runtime — just Markdown any
agent that reads instruction files can follow. The router
(`using-fan-development-skills`) is the single source of truth for how the toolkit
behaves: every action skill reads and applies it before doing anything else, so
the same judgment — flag uncertain evidence instead of inventing it, push back on
a weak segment instead of validating it, don't chain forward without a check-in —
shows up whether you invoke one skill or run the whole flow.

Each skill searches the web when a search capability is available in your
session — to gather research on an unfamiliar business, or to ground a recommendation in
real information — and asks you to share material instead if search isn't available or limited.

Every brief is also saved to a file in your project, under `fan-development/`,
and read back in automatically the next time a skill runs for that business or
segment — so picking up `/awareness` in a fresh session after running
`/research` in an old one doesn't require re-explaining anything. 

## Why this exists

Most growth advice defaults to a tactic — run a campaign, launch a partnership,
try a giveaway — before anyone's confirmed which stage of the funnel is actually
broken. Awareness fixes don't help a segment that already knows you and never
converts. Integration mechanics don't help a segment that doesn't know you exist
yet. The mismatch is where budget and goodwill get wasted.

This toolkit forces the diagnosis first, and keeps a few disciplines non-negotiable
across every stage after it:

- **Weighted scoring over vibes.** Candidate segments are scored on eight
  dimensions, not ranked by whatever feels right in the room.
- **Flag uncertainty instead of inventing confidence.** If the evidence for a
  claim is thin, the output says so — `LOW_EVIDENCE`, no made-up numbers.
- **The metric to track must move the needle.** Every brief names a metric
  you'd actually need to convince someone holding the budget, not what's
  easiest to report.
- **Context is explicit, not implied.** A recommendation without a sense of
  timing, team capacity or product perception isn't helpful.

## License

MIT — see [LICENSE](LICENSE).
