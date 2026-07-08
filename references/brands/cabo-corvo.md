---
brand_id: cabo-corvo-series
series_title_onscreen: "The Real Housewives of Cabo Corvo"   # fictional; safe to publish
working_title_internal: "[private reference only — never ship]"
format: youtube_shorts
aspect_ratio: "9:16"
duration_seconds_max: 60
target_hook_seconds: 1.5
episodes_per_batch: 5
animation_style: "full character animation, avatar-based"   # decided 2026-07-08 — see Locked format
tooling_candidates: "HeyGen (subscription + API), ElevenLabs, vidIQ voiceover"
narration: "third-person narrator + minimal dialogue"
voices: "TBD — decide after episode-1 prototype"
tone: "warm satire, never cruel"
language_primary: "en"          # subtitle/localize to gl/es as needed
publish_gate: "human_required"  # automation stops before publish
---

# The Real Housewives of Cabo Corvo — brand file

A satirical animated Shorts series. Tone: *Desperate Housewives* ×
*Aquí no hay quien viva*. This file is the single source of truth for any
content-production skill. Everything downstream (script → voice → animation →
assembly) must conform to it. **The Fictionalization Firewall is a hard
constraint, not a guideline.**

## Identity

An outsider woman — sharp, striking, and completely unaware of it — lands in a
small Galician dock town, buys a crumbling stone house, fills it with goats and
chickens, and gets pulled into the town's endless tangle of affairs, rituals,
and drunk-philosophical terrace conversations. She keeps swearing she's above
the drama. She is not. The promise to the viewer: one perfectly-shaped small
absurdity per episode, warm enough to live in.

## THE FICTIONALIZATION FIREWALL *(hard constraint — enforced at every stage)*

The source material is drawn from real life in a real small town. The
production output must **never** be traceable to real people. Any skill
consuming this file MUST obey:

- **Invented world only.** The town is **Cabo Corvo**; the central barrio is
  **O Curruncho**. These are fictional. Never output the real town name, real
  place names, or real business names — not in scripts, captions, titles,
  tags, or metadata. (This includes repo artifacts: filenames, commit
  messages, queue entries.)
- **Composite characters only.** Every character is a blend, never a portrait.
  If a script would let a real individual recognize *themselves specifically*,
  blur the identifying detail (job, physical marker, exact incident) until
  it's an archetype, not a person.
- **No real names, ever** — including the creator's own, in-world.
- **Swap identifying specifics for genre-typical ones.** Keep the emotional
  truth and the comic mechanic; change the fingerprint (change the boyfriend's
  exact job, the exact village, the exact party).
- **Publish gate is human.** Automation may draft, voice, and assemble a
  Short. It may NOT auto-publish. A human reviews every episode against this
  firewall before release. No exceptions.

If any generation step is uncertain whether a detail is identifying, it treats
it as identifying and blurs it.

## Voice

Warm satire, never cruel. Comedy rules:

- **Warm, not cruel.** We laugh *with* the town, never punch down. The butt of
  every joke is human folly everyone shares — vanity, self-deception, the
  inability to leave a bad loop — not a specific person's dignity.
- **The protagonist is the primary fool.** She's self-aware enough to narrate
  her own bad decisions and make them anyway. That's the engine. The funniest
  version of a beat is usually the more *embarrassing* one (the relapse, not
  the revenge).
- **Contradiction is character.** Every recurring role carries a visible gap
  between how they appear and who they are.
- **Universal hook required.** Every episode must land on one feeling any
  viewer anywhere recognizes, even knowing nothing about Galicia.
- No cruelty about bodies, real tragedy, or anything that reads as a real
  accusation about a real person.

Lines that ARE the voice: self-narrated bad decisions ("I told them I was
above this. I brought a chair."). Lines that are NOT: anything mean-spirited,
anything winking at a real person, anything that needs local knowledge to land.

## Running thesis

None. The recurring engine is the protagonist's contradiction (most self-aware
person in town, least self-aware choices), not an argument. Do not thread an
external thesis into episodes.

## Locked format

- **Platform:** YouTube Shorts (portrait 9:16, ≤60s). Optimized to also cut
  for TikTok/Reels.
- **Hook:** the funniest or most destabilizing beat lands inside the first
  ~1.5 seconds. No slow build. Cold open on the absurdity.
- **Structure per Short:** Hook (0–1.5s) → Escalation (mid) → Punchline/button
  (end). One idea per Short.
- **No spoken sign-off** — every episode ends on the punchline/button.
- **Animation style — DECIDED (2026-07-08): full character animation,
  avatar-based.** Each of the six recurring characters gets a fixed avatar
  (HeyGen subscription + API available), which is what makes full animation
  viable despite the consistency risk that made motion-comic the original
  recommendation: the avatar IS the consistency mechanism. The "never break
  ensemble visual consistency" rule now means: one locked avatar per
  character, reused every episode, no regeneration.
- **Visual identity — A/B at prototype:** two candidate looks, to be locked
  after the episode-1 prototype: (a) warm European comic styling applied to
  the avatars, or (b) the avatars' native/realistic look. Whichever ships in
  episode 1 becomes the locked look for the season.
- **Narration — DECIDED:** a wry third-person narrator carries each episode;
  characters get one or two dialogue lines at most.
- **Voices — OPEN:** decide after hearing the episode-1 prototype with
  placeholder voices. Candidates: HeyGen built-in voices, ElevenLabs, vidIQ
  voiceover clone. Firewall note: if the creator's own cloned voice is ever
  used, it stays unnamed in-world.

## Cutdown rules

The Short IS the unit — there is no long-form master. TikTok/Reels cuts keep
the same ≤60s episode; only reframe/captions may change. Hook stays inside
1.5s in every cut. The human publish gate applies to every platform version.

## Topics & boundaries

**Recurring engines** to reuse as episode settings: the Sunday eat-all-day
ritual; percebes/seafood treated as everyday luxury; the gravity-well bar
where nights never end ("the black hole"); the surf-and-fashion crowd; terrace
philosophy that's really just being drunk in the sun.

**Character bible** *(composite archetypes — no real individuals)*:

- **⭐ The Outsider (protagonist):** A foreigner who runs a small farm of
  goats, chickens and sheep, sharp and striking but oblivious to it, more
  comfortable with men and mud than with her own femininity. Swears she's
  above the town's drama; is its most reliable participant. *Contradiction:
  the most self-aware person in town, making the least self-aware choices.*
- **⭐ The Harpoon:** The good-looking dock-town charmer who works through the
  whole barrio — married, engaged, no matter — while two lesser men study him
  like a failed apprenticeship. *Contradiction: everyone knows he's bad news
  and orbits him anyway.*
- **⭐ The Chair (the hairdresser):** Beautiful, singing, center of every
  room; knows every secret because everyone confesses in her chair; quietly
  the loneliest person in town. *Contradiction: life of the party, alone in
  the crowd.*
- **⭐ Forever 29 (the housemate):** A free spirit in her fifties, dragged
  into a grandmotherhood she never ordered, waging a one-woman war on aging.
  *Contradiction: refusing the role life keeps casting her in.*
- **⭐ The Two Brothers (beach chiringuito):** The short, unglamorous "clever
  businessman" and the tall, handsome one written off as a dim hippie — who is
  secretly the deepest reader and thinker in the barrio. *Contradiction: the
  one everyone underestimates is the wisest, and prefers it that way.*
- **⭐ The Rasta Sage:** An older, multifaceted neighbor — teacher, botanist,
  musician, keeper of many dogs and quiet wisdom. The town's gentle
  philosopher. *Contradiction: looks like the least serious man in town, is
  the most grounded.*

**Setting bible:** **Cabo Corvo** — a small, weather-beaten Atlantic port
town. **O Curruncho** is its central barrio: a boutique hotel-restaurant
beside the protagonist's stone house (the social black hole), terraces in the
sun, a beach chiringuito that turns into a techno party, a working port, surf
breaks, and a hinterland of tiny villages. The town itself is a character: it
eats all Sunday, treats luxury as ordinary, and never lets anyone leave a
conversation — or a bad relationship — cleanly.

**Episode entry format** *(what the Story Catcher feeds this pipeline)* —
situations arrive pre-fictionalized in this locked shape:

```
- ⭐ [title]: [2–4 sentence funny shape, no real names/places].
  Universal hook: [feeling]. Comic escalation: [how to blow it up].
```

The production skill turns one entry → one Short, obeying the Firewall, Voice,
and Locked format sections.

**Hard "Never" list for the production skill:**

1. Never output a real name or real place (Firewall).
2. Never auto-publish — stop at the human gate (Firewall).
3. Never punch down or make a real-sounding accusation about a real person (Voice).
4. Never exceed 60s or bury the hook past ~1.5s (Locked format).
5. Never break ensemble visual consistency across episodes (Locked format).

## Live examples (grow this over time)

| Hook / Title (as shipped) | Type | Why it earned the watch | Performance |
|---|---|---|---|
| | | | |
