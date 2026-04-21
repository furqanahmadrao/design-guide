# design-guide

A Claude skill that gives any AI agent a structured, opinionated design pipeline — from extracting a design system out of any URL or screenshot, to ideating original concepts from scratch, to shipping a live design system preview before a single line of UI is written.

Works in any Claude environment. No hardcoded paths, tool names, or platform assumptions.

---

## What it does

Give it a URL, a screenshot, or a product idea. It runs a full design pipeline:

```
Input
  ↓
Extract from reference  ──or──  Ideate from idea
  ↓
Design system spec (tokens, components, layout, creative core)
  ↓
Live design system preview artifact  ←  user approves here
  ↓
Build UI
  ↓
Package .skill file with chosen design baked in
```

---

## Paths

**Extraction** — URL, screenshot, Figma file, or any visual reference. Extracts the design system layer by layer: color, typography, spacing, shape, components, motion, accessibility. Produces a fully populated spec.

**Ideation** — a product idea or description. Reads every available design-related skill in your environment before generating concepts. Produces 3 genuinely distinct design concepts with enforced divergence across light/dark, density, personality, and typography axes. You choose one, or blend.

**Hybrid** — both. Reference provides visual truth. Idea fills gaps and provides product context.

---

## The preview

Before anything is built, the skill renders a live HTML design system preview page:

- Color palette with every token labeled
- Typography scale — H1 through caption through mono
- Spacing scale as a visual ruler
- Component showcase — buttons, inputs, cards, badges, loading states — rendered and interactive via CSS hover
- Layout structure sample
- Creative core callout

The page **styles itself using its own token system**. It is a live demonstration, not a spec dump. Nothing is built until the user approves this preview.

---

## Install

Download the latest `.skill` file from [Releases](../../releases) and install it in your Claude environment.

Or install from source:

```
skill/
├── SKILL.md                     ← main pipeline and rules
├── methodologies/
│   ├── extraction.md            ← 6-phase extraction process
│   └── ideation.md              ← 6-phase ideation process
├── references/
│   ├── design-tokens.md         ← full CSS token schema
│   ├── component-index.md       ← component documentation format
│   ├── layout-patterns.md       ← grid and page structure rules
│   ├── brand-notes.md           ← identity, principles, voice
│   ├── implementation-notes.md  ← frontend constraints
│   └── examples.md              ← quality criteria and anti-patterns
└── templates/
    └── preview-artifact.html    ← HTML scaffold for design system previews
```

---

## How the output skill works

When you ask it to package the design, the output `.skill` file contains the full chosen design system baked into the reference files — all tokens populated, all components documented, creative core stated. An agent receiving the skill can build the correct UI without re-doing ideation or re-extracting from the original reference.

---

## Key rules the skill follows

- Reads every available design-related skill during ideation, before generating any concepts — not at build time
- Never builds before the user approves the design system preview
- Never skips the preview even if explicitly asked to
- Packs the full chosen design system into the output `.skill` file
- Never hardcodes paths, tool names, or environment-specific assumptions
- Explicitly rejects generic AI aesthetics — predictable fonts, purple-on-white gradients, symmetric layouts with no creative decision

---

## License

MIT — see [LICENSE](LICENSE).
