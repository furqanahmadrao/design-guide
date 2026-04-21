# Ideation Methodology

Use this when input is: a text description, product idea, feature request, or brief
with no visual reference provided.

This methodology is read AFTER all available design-related skills have been read.
The creative vocabulary from those skills informs the concepts generated here.

---

## Phase 1 — Understand Before Designing

Do not make any design decisions yet. First understand the problem.

Ask clarifying questions using the `ask_user_input_v0` tool.
Maximum 3 questions per round. Never ask in plain text.

### Round 1 — Product and Users (always run this round)

Derive the options from the user's idea — do not use generic placeholders.

```
Q1: What is the primary purpose of this product?
    Options: [4 specific options derived from the idea] + "Something else"

Q2: Who is the primary user?
    Options: [4 specific user types derived from the idea] + "Other"

Q3: What feeling should the UI create?
    Options: Focused and efficient / Warm and approachable / Bold and expressive /
             Clean and minimal / Playful and energetic / Professional and serious
```

### Round 2 — Design Direction (run if still ambiguous after Round 1)

```
Q1: What color direction feels right?
    Options: Dark / Light / High contrast / Muted and subtle /
             Brand color dominant / No preference

Q2: What density level fits this product?
    Options: Information-dense (a lot visible at once) /
             Comfortable (balanced) /
             Spacious (generous breathing room)

Q3: Name any product UI you like the look of.
    [Free text or common product options if open text is unavailable]
```

### Round 3 — Constraints (run only if technical context matters)

```
Q1: What is this being built for?
    Options: Web app / Mobile app / Desktop app /
             Marketing site / Dashboard / Component library

Q2: Any technical constraints?
    Options: Must be React / Must be plain HTML and CSS /
             Framework does not matter / Other
```

Stop asking once you have enough to generate 3 genuinely distinct concepts.
Do not over-question.

---

## Phase 2 — Find the Gap

Before generating concepts, identify the design direction that is underexplored
in this product category.

1. Name 3 well-known products in the same category
2. Note the dominant design direction each uses
3. Note what none of them do
4. The gap is where the most interesting concept lives

The best concept is rarely the obvious one for the category.

---

## Phase 3 — Generate 3 Distinct Concepts

Generate exactly 3 concepts. They must represent genuinely different design philosophies
applied to the same product — not the same idea with different colors.

For each concept define:

```
CONCEPT [N]: [Name — 2–3 evocative words]

Philosophy:       [One sentence — the visual idea behind this concept]

Aesthetic:        [adjective], [adjective], [adjective]

Color palette:
  Background:     [hex value]
  Surface:        [hex value]
  Accent:         [hex value]
  Text:           [hex value]
  Mood:           [one word]

Typography:
  Heading:        [font style + specific font name]
  Body:           [font style + specific font name]
  Special choice: [any unusual or deliberate pairing decision]

Layout:           [grid, density, structure description]

Creative core:    [The one thing that makes this concept unforgettable]

Anti-values:      [What this concept would never do]

Best for:         [Which user or context this serves best]
```

### Divergence Rules

The 3 concepts must occupy different positions in design space:

| Axis | Spread required |
|---|---|
| Light / Dark | All three must differ — at least one dark, one light |
| Density | Cover the range: dense, balanced, spacious |
| Personality | Cover the range: serious, neutral, expressive |
| Typography | No two concepts share the same heading font or font style |
| Layout | At least one must break from the conventional structure for this product type |

If any two concepts feel similar, replace the weaker one.

---

## Phase 4 — Render Concept Preview Cards

Render all 3 concept cards as a single HTML artifact.
Read `templates/preview-artifact.html` for the card scaffold — use Section A.

Each card shows the design system for that concept:
- Color swatches with hex values and token names
- Typography sample — heading and body text rendered in the actual fonts
- Primary button in the concept's style
- Sample card in the concept's style
- Badge variants
- One loading state indicator
- Creative core callout labeled visibly

Cards appear side by side on a neutral background.
The artifact uses inline styles or scoped CSS per card — each card is self-contained.

Present the artifact, then ask using `ask_user_input_v0`:

```
Q: Which concept direction resonates most?
   Options: [Concept 1 name] / [Concept 2 name] / [Concept 3 name] /
            Blend [1 + 2] / Blend [2 + 3] / Blend [1 + 3] /
            I want a different direction
```

---

## Phase 5 — Refine the Selected Concept

**If one concept selected:**
Expand it into the full design system spec — every token, every component.
Ask one follow-up question only if something critical is still ambiguous.

**If a blend selected:**
State explicitly which elements come from each concept.
Show a revised preview card of the blend before producing the full spec.

**If different direction requested:**
Ask what specifically to change: color / typography / density / layout / all of it.
Generate 1–2 targeted new concepts addressing the feedback.
Show mini previews and ask again.

---

## Phase 6 — Produce Full Design System

After the concept is confirmed, produce:

1. Full design system spec — every token filled (schema in `references/design-tokens.md`)
2. Component inventory — full variants and states (format in `references/component-index.md`)
3. Design principles — 3–5 derived from the chosen concept's philosophy
4. Creative core statement — one sentence, specific
5. Layout rules — grid, container, nav pattern, section rhythm

Hand off to Step 3 of the main pipeline.

---

## Concept Quality Bar

**Strong concept:**
- Has a visual philosophy expressible in one sentence
- Makes at least one unexpected creative choice for the product category
- Colors, typography, and layout all serve the same idea — internally consistent
- Would look different from every other product in the same category

**Weak concept — do not proceed with it:**
- Philosophy is "clean and minimal" with no further definition
- Uses the most common font choices for the category
- Could apply to any product — no specificity to this one
- Has no creative core

If a concept is weak, replace it before presenting to the user.
