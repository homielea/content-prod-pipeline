# Content production pipeline

Reusable content-production Skills plus the brand files and production queue
they operate on.

## Layout

- **`landing-pass/`** — the hook-mining editor Skill. Raw transcript → diagnosis
  → 5 rubric-typed hooks (mined, not generated) → script in the brand's locked
  format → weakest-line flag.
- **`content-engine/`** — the channel-agnostic production spine. Raw material +
  brand + format → landing-pass hook → master script → platform cutdowns →
  vidIQ-scored titles + thumbnail concepts. The brand-file contract lives at
  `content-engine/references/brand-template.md`.
- **`references/brands/`** — one file per brand; the ONLY place channel-specific
  voice, format, thesis, or sign-off lives. Current: `leas-lessons.md`,
  `cabo-corvo.md`.
- **`production/queue/`** — finished scripts waiting to be recorded/produced.
  One file per piece, status at the top. After shipping, log hook + title +
  performance into the brand's live-examples table.
- **`dist/`** — packaged `.skill` files (zip archives of each skill directory).
- **`*/tests/`** — real-material validation runs for each skill.

## Workflow

1. Record / collect raw material.
2. Run **content-engine** with a brand + target format (it calls
   **landing-pass** for the hook).
3. Review the package, then drop the approved script into
   `production/queue/` as `YYYY-MM-DD-<slug>.md`.
4. Record and publish (Cabo Corvo: human publish gate is mandatory).
5. Log what shipped and how it performed in the brand file's live-examples
   table — that's how the system compounds.
