---
name: content-engine
description: >-
  Channel-agnostic content production spine. Takes raw material (a walk-and-talk
  transcript, notes, or a rough draft), a target brand, and a target format, and
  runs the full production chain: mine the hook with the landing-pass skill,
  draft the master script to the brand's locked format, cut platform versions
  (long-form + Shorts/TikTok), and produce title and thumbnail options scored
  via vidIQ. All voice, format, thesis, and sign-off rules are read from
  references/brands/<brand>.md — no channel is ever hardcoded. Use when turning
  raw material into a full publishable content package, when producing platform
  cutdowns from a master script, or when generating scored title/thumbnail
  options for a drafted video.
---

# Content Engine

The production spine. One pass takes raw material to a publishable package:
hook → master script → platform cutdowns → titles/thumbnails. Every
brand-specific decision comes from a brand file; this skill only knows the
*process*.

## Inputs (all three required)

1. **Raw material** — transcript, voice-note dump, notes, or rough draft.
   Rambly is fine; the hook step expects it.
2. **Target brand** — a name resolving to `references/brands/<brand>.md`
   (looked up from the repo/project root). **This file is the single source of
   truth for voice, locked format, thesis, sign-off, and cutdown rules. If it
   doesn't exist, STOP and ask — never improvise a brand voice, and never
   default to any particular channel.** The required shape of a brand file is
   in [references/brand-template.md](references/brand-template.md).
3. **Target format** — what to produce: `long-form`, `shorts` (Shorts/TikTok/
   Reels), or `full package` (both + titles/thumbnails). Default to
   `full package` if the user doesn't say.

## The chain

Run the stages in order. Each stage's output feeds the next. Show the user the
output of each stage as you go — this is a production line they steer, not a
black box.

### Stage 1 — Load the brand

Read `references/brands/<brand>.md` in full. Everything downstream obeys it.
Where a brand rule and a generic best practice conflict, the brand rule wins.

### Stage 2 — Land the hook (landing-pass)

Run the **landing-pass** skill on the raw material with this brand's brief:
diagnosis → mined hooks (5, rubric-typed, mined/tightened/forged-labeled) →
recommended hook → weakest-line flag. If landing-pass is not installed, follow
its procedure from `landing-pass/SKILL.md` in this repo.

Pause here if the user wants to pick the hook themselves; otherwise proceed
with the recommended one.

### Stage 3 — Draft the master script

Using the chosen hook, write the master script exactly to the brand's locked
format — structure, timing, prose rules, thesis-weaving rules, and the exact
sign-off all come from the brand file. The master is the longest version the
material honestly supports; cutdowns are derived from it, never the reverse.

Mining discipline carries over from landing-pass: prefer the speaker's actual
phrases from the raw material over invented ones, everywhere — not just in the
hook.

### Stage 4 — Platform cutdowns

From the master, produce the versions the target format calls for:

- **Long-form** — the master script, plus a one-line description of the
  intended pacing (where the energy rises, where to slow down).
- **Shorts/TikTok/Reels** — cap near 1 minute. Lead with an even sharper hook
  than the master (re-mine from the hook list; the runner-up hook often works
  better at short length). Cut setup, keep the turn, keep the brand's sign-off
  unless the brand file says otherwise. If the master contains more than one
  self-contained idea, offer one cutdown per idea rather than one compressed
  blur.

A cutdown is an *edit*, not a summary — it should feel like the best 45 seconds
of the master, not a compressed retelling of all of it.

### Stage 5 — Titles & thumbnails (vidIQ)

Produce 3–5 title options and 2–3 thumbnail concepts:

1. Generate candidates with the vidIQ tools when available
   (`vidiq_generate_titles`, then `vidiq_score_title` on each; use
   `vidiq_keyword_research` when the topic has search intent, and
   `vidiq_generate_thumbnail` / `vidiq_score_thumbnail` for thumbnail
   concepts). Report the scores next to each option.
2. Titles must survive the same kill conditions as hooks (see the landing-pass
   Hook Rubric) — a high vidIQ score does not save a title that's generic or
   AI-clever. Say so when you kill a high-scoring candidate.
3. If vidIQ is unavailable, still deliver title options mined from the hook
   list, clearly marked **unscored**, and note the user can re-run scoring
   later.

Thumbnail concepts are described in words (composition, text overlay ≤4 words,
emotion) unless the user asks for generated images.

## Output package

Deliver the final package in this shape:

```
BRAND: <brand> (from references/brands/<brand>.md)
HOOK: [Type] "<hook>" — <provenance>   (+ MATERIAL NOTE if landing-pass raised one)

MASTER SCRIPT:
<locked-format script>

CUTDOWNS:
<one per requested platform>

TITLES:
1. "<title>" — vidIQ score <n> (or: unscored)
...

THUMBNAILS:
1. <concept>
...

FLAGS: <weakest line + anything the user should fix before recording>
```

## After the run

Remind the user to log the hook and title that actually shipped (and later, how
they performed) into the brand file's live-examples table. The engine gets
smarter only if the brand files compound.
