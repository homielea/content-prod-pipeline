---
name: story-catcher
description: >-
  Fictionalizing story intake for serialized comedy content. Takes raw lived
  material — a voice-note ramble, an anecdote, "you won't believe what happened
  last night" — and turns it into safe, pre-fictionalized story-bank entries in
  a target brand's locked entry format: real people mapped onto the brand's
  composite character archetypes, identifying details blurred per the brand's
  fictionalization rules, the comic mechanic and universal hook made explicit.
  Entries are appended to production/story-bank/<brand>.md as the feedstock the
  content-engine turns into episodes. Use when capturing real-life anecdotes or
  town gossip as future episode material, when converting a raw personal story
  into a publishable fictional shape, or when reviewing story material for
  identifying details before production. Reads all world, character, tone, and
  firewall rules from references/brands/<brand>.md — never hardcoded to one
  series.
---

# Story Catcher

The intake end of the pipeline. Life produces the material; this skill catches
it, de-identifies it, and banks it in episode-ready shape. One rambling
voice note in → one or more story-bank entries out, each safe to hand to the
production engine.

## The one rule: keep the truth, change the fingerprint

The comedy is only good because it really happened — the emotional truth and
the comic mechanic are the gold. **Never invent drama that wasn't in the
material, and never keep a detail that points at a real person.** Fictional
fingerprints, real folly.

This is the same editor-not-generator discipline as landing-pass, applied to
story: mine the actual absurdity the teller lived; don't write sitcom.

## Inputs

1. **Raw material** — an anecdote in any form: transcript, voice-note dump,
   chat ramble, a half-remembered night. Real names and real places in the
   input are expected; removing them is this skill's job.
2. **Target brand** — resolves to `references/brands/<brand>.md`. The brand
   file supplies the fictional world, the composite character bible, the tone
   rules, the fictionalization/safety constraints, and the locked entry
   format. **If the brand file is missing, or lacks an entry format or
   fictionalization rules, STOP and ask — never improvise a safety rule.**

## The procedure

1. **CATCH** — Read the whole ramble. Extract EVERY distinct story seed; one
   voice note usually holds two or three, and the best one is often the aside,
   not the story the teller thinks they're telling. List the seeds back in one
   line each.

2. **FIND THE MECHANIC** — For each seed worth keeping: name the comic
   mechanic (the loop, the contradiction, the escalation that makes it funny)
   and the **universal hook** — the one feeling any viewer anywhere recognizes
   with zero local context. A seed with no universal hook gets parked, not
   forced.

3. **FICTIONALIZE (the firewall pass)** — Apply the brand's fictionalization
   rules to every kept seed:
   - Strip every real name, real place, real business — replace with the
     brand's invented world.
   - Map each real person onto the brand's composite archetypes. If nobody in
     the character bible fits, draft a NEW composite archetype (blend of at
     least two real people, genre-typical details) and flag it as a proposed
     brand-file addition — never a portrait of one person.
   - Swap identifying specifics for genre-typical ones: change the job, the
     village, the exact party. Keep the emotional truth and the mechanic.
   - **When uncertain whether a detail is identifying, it is identifying —
     blur it.**

4. **SHAPE** — Write each entry in the brand's locked entry format, exactly.
   Tone rules apply already at entry level (e.g., warm not cruel; the
   protagonist as primary fool; the embarrassing version over the revenge
   version).

5. **SELF-RECOGNITION CHECK** — Re-read each entry as the real person
   involved would. Could they recognize *themselves specifically* — not "people
   like me" but "that is me"? If yes, blur harder and re-check. Also confirm:
   nobody's dignity is the joke, no real-sounding accusation, nothing about
   bodies or real tragedy.

6. **BANK** — Append the surviving entries to
   `production/story-bank/<brand>.md` with today's date and status `new`.
   Statuses: `new` → `approved` (human reviewed it against the brand's
   firewall) → `produced` (episode shipped, link it). Only a human moves an
   entry to `approved` — this skill never does.

## Output format

```
SEEDS CAUGHT: <n> (<one line each, including any parked for no universal hook>)

ENTRIES:
<each in the brand's locked entry format>

FICTIONALIZATION LOG:
<per entry, one line: what was blurred/swapped — so the human reviewer can
judge whether it's blurred enough. Never write the real detail itself into
this log; describe the category ("swapped the job", "merged two people").>

PROPOSED ARCHETYPES: <only if step 3 created one — flagged for the brand file>

PARKED: <seeds kept aside and why, so material is never silently lost>
```

## What this skill never does

- Never invents events that were not in the raw material.
- Never writes a real name or real place into any output, including logs.
- Never marks its own entries `approved` — the human review gate is the
  brand's, not the skill's.
- Never discards a seed silently — parked seeds are listed with reasons.
