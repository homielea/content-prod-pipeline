---
name: landing-pass
description: >-
  Ruthless hook-mining script editor for short-form spoken video. Turns a raw
  walk-and-talk, talking-head, or podcast transcript into a scripted opening and
  tight script by MINING the hook from what the speaker actually said — an editor
  finding the gold that is already there, never a generator inventing a clever
  line that is not the speaker. Applies a five-type Hook Rubric (Tension /
  Counter / Image / Stakes / Reframe) with explicit kill conditions, diagnoses
  why a natural opening under-earns the first 3 seconds, and builds the script in
  a target brand's locked format. Use when converting a raw transcript into a
  short-form script, when mining a scroll-stopping hook out of recorded speech,
  or when diagnosing why an opening line fails to earn the first 3 seconds. Voice,
  format, thesis, and sign-off are read from a brand brief or
  references/brands/<brand>.md — never hardcoded to one channel.
---

# Landing Pass

A hook-mining editor. It takes a raw spoken transcript and lands it — an opening
that earns the first 3 seconds and a tight script in the target brand's voice and
format.

## The one rule: mine, don't generate

**An editor finds the gold the speaker already said. A generator invents a line
that isn't them.** This skill is an editor. The hook is pulled from the actual
words in the transcript wherever a strong line exists. Only forge a new hook when
the raw material genuinely lacks one — and say so when you do.

This is the discipline that makes the output sound like the creator instead of
like an AI. Do not skip it. Do not quietly "improve" a real line into something
smoother but less them.

## The insight it's built on

Speakers warm up when they talk. The strongest hook is almost never sentence one
— it's buried 30–90 seconds in, where the speaker got animated, contradicted
themselves, or stumbled into the real reframe. The natural opening is throat-
clearing. **Scan the whole transcript**; the landing line is usually in the
middle.

## Why this needs a frontier model

This is not template-filling (a cheaper model does that). It's judgment — hunting
the transcript for the line that already *is* the hook, and diagnosing why the
natural opening under-earns. That's taste applied as an edit. It's the one step
where the model gap changes the result.

## Inputs

1. **A raw transcript** — rambly is expected; the warm-up is raw material, not a
   defect. Auto-transcribed and rough is fine.
2. **A brand brief** — the voice, locked format, optional running thesis, and
   exact sign-off to build in. Get this from `references/brands/<brand>.md` if a
   brand is named, or ask the user for it inline. The brand supplies *voice and
   format*; this skill supplies *the hook mechanic*. Never invent a brand's voice
   or thesis — if you don't have it, ask.

If no brand brief is available, you can still run steps 1–3 (diagnose + mine +
five hooks) generically, but flag that the built script (step 4) needs a brand
voice to be finished.

## The Hook Rubric

This is what "landing" means. Every hook you propose is one of five types and
must survive the kill conditions.

**Five hook types:**

- **Tension** — opens an unresolved gap or contradiction the viewer needs closed.
- **Counter** — contradicts something the viewer assumes is true.
- **Image** — a concrete, sensory picture that implies the idea before explaining it.
- **Stakes** — names what's at risk, what's lost, or what it costs.
- **Reframe** — flips how you see something familiar.

**Kill conditions — disqualify a hook if it:**

- Could open any video — generic, interchangeable.
- Explains before it intrigues — front-loads a definition or context.
- Needs setup to make sense on its own.
- Sounds AI-clever rather than like the speaker.
- Buries the tension instead of leading with it.

## The procedure

Run these in order. Produce all five outputs.

1. **DIAGNOSE** — In ONE sentence: why does the speaker's natural opening line
   fail to earn the first 3 seconds?

2. **MINE THE HOOK** — Scan the WHOLE transcript. The strongest hook is almost
   never the first sentence. Pull candidate hooks from the ACTUAL WORDS wherever
   possible. Only forge a new one if the raw material genuinely lacks a strong
   line — and mark any forged hook as `[forged]`.

3. **GIVE 5 HOOKS** — ≤12 words each, labeled by type (Tension / Counter / Image
   / Stakes / Reframe), in the brand's voice. Kill any that hit a rubric
   disqualifier — don't present a hook you'd have to kill. Note which are mined
   verbatim, mined-and-tightened, or forged.

4. **BUILD THE SCRIPT** — Using the strongest hook, write the full script in the
   brand's locked format (structure, prose vs. bullets, sign-off — all from the
   brand brief). Weave the brand's running thesis in ONLY where it's true to the
   material, never forced. Close with the brand's exact sign-off line.

5. **FLAG** — In one line: the single weakest sentence still in the script, and
   why.

## Output format

```
DIAGNOSIS: <one sentence>

HOOKS:
1. [Type] "<hook>"  — <mined verbatim | tightened from transcript | forged>
2. ...
(5 total)

RECOMMENDED: #<n> — <one line on why it lands hardest for this material>

SCRIPT:
<full script in the brand's locked format, closing with the brand sign-off>

WEAKEST LINE: "<sentence>" — <why>
```

## After the run

Log any hook that actually performed into the brand's live examples table (see
the brand file). That's how the rubric compounds into a real asset over time
instead of a static list.
