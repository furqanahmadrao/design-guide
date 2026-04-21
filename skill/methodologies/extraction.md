# Extraction Methodology

Use this when input is: URL, screenshot, UI mock, Figma file, or any visual reference.

---

## Phase 1 — Acquire the Reference

### If URL given
1. Fetch the URL using your web fetch tool
2. Capture navigation, hero, content sections, and footer
3. Note which state was captured — fetch returns one snapshot, not all states
4. Mark every value that required inference as `[inferred]`

### If screenshot given
1. Analyze the image — do not guess at off-screen content
2. Note the viewport size if inferrable
3. Mark every value not directly visible as `[inferred from visual]`

### If Figma or mock given
1. Read all visible layers, styles, and annotations
2. Extract exact values where specified
3. Document what states or components are absent from the mock

---

## Phase 2 — Gestalt Read First

Before extracting any specific values, form an overall impression.
Answer these 7 questions as a single paragraph:

1. What is the dominant emotion this UI communicates?
2. Who is clearly the target user?
3. Is this high-density or low-density?
4. Where does visual weight concentrate?
5. What is the single most distinctive visual choice?
6. Does this feel like a tool, a product, or an experience?
7. What would this UI never do — its anti-values?

This paragraph becomes the **Design Extraction Summary**.

---

## Phase 3 — Layer-by-Layer Extraction

Work through every layer in order. Do not skip any layer.

### Layer 1 — Color System

```
Backgrounds:
  Page background:        [value]  [observed / inferred]
  Card / surface:         [value]
  Raised surface:         [value]

Text:
  Primary:                [value]
  Secondary / muted:      [value]
  Disabled:               [value]

Accent:
  Primary accent:         [value]  used for: [buttons / links / highlights]
  Secondary accent:       [value or none]
  Accent hover state:     [value or description]

Semantic:
  Danger / error:         [value or not observed]
  Success:                [value or not observed]
  Warning:                [value or not observed]
  Info:                   [value or not observed]

Borders:
  Default:                [value]
  Strong:                 [value]

Mode: light / dark / auto
```

### Layer 2 — Typography

```
Heading font:
  Family:                 [name, or "unidentified — [description]"]
  Style:                  geometric sans / humanist / serif / slab / monospace / display
  H1:                     size, weight, line-height, letter-spacing
  H2:                     size, weight, line-height
  H3:                     size, weight, line-height

Body font:
  Family:                 [name]
  Base size:              [value]
  Line height:            [ratio]
  Weight:                 [value]

Additional:
  Mono (code / data):     [name or not present]
  Caption / label size:   [value]
  Letter spacing tendency: tight / normal / wide
  Pairing logic:          same family / two families / one family only
```

### Layer 3 — Spacing and Layout

```
Grid:
  Column count:           [number]
  Gutter:                 [value]
  Container max-width:    [value]
  Edge margin / padding:  [value]

Spacing scale pattern:
  Smallest gap observed:  [value]
  Component padding:      [value]
  Between components:     [value]
  Section spacing:        [value]
  Base unit:              4px / 8px / custom [value]

Navigation:
  Type:                   topbar / sidebar / bottom / none
  Height or width:        [value]
  Sticky:                 yes / no
  Mobile pattern:         [if observable]

Content structure:
  Card-based or flat:     [answer]
  Full-width or contained: [answer]
  Sidebar present:        yes / no
```

### Layer 4 — Shape and Depth

```
Border radius:
  Buttons:                [value]
  Cards:                  [value]
  Inputs:                 [value]
  Modals:                 [value]
  Overall tendency:       sharp / soft / pill

Shadows:
  Card shadow:            [value or none]
  Elevated component:     [value or none]
  Modal overlay:          [value or none]
  Philosophy:             flat / subtle / pronounced / none

Borders on components:
  Cards have borders:     yes / no
  Border width:           [value]
  Border style:           solid / dashed / none
```

### Layer 5 — Component Inventory

```
Buttons:
  Primary:                [describe]
  Secondary:              [describe]
  Ghost / text:           [describe or not present]
  Sizes observed:         sm / md / lg
  States observable:      hover / active / disabled / loading

Inputs:
  Style:                  outlined / filled / underline / floating label
  Focus treatment:        [describe]
  Error state:            [describe or not observed]

Cards:
  Shadow:                 [value]
  Radius:                 [value]
  Internal padding:       [value]
  Hover behavior:         lift / highlight / none

Navigation:
  Active state:           [describe]
  Icons present:          yes / no
  Collapsed state:        [if observable]

Other components observed:
  Badges / chips:         [describe]
  Tables:                 [describe]
  Modals:                 [describe]
  Tabs:                   [describe]
  Loading states:         spinner / skeleton / shimmer / not observed
  Empty states:           [describe or not observed]
```

### Layer 6 — Motion and Interaction

```
Transition speed feel:    instant / fast / moderate / slow
Easing feel:              sharp / smooth / bouncy
Hover — buttons:          [describe change]
Hover — cards:            [describe or none]
Hover — links:            [describe]
Interaction density:      dense / medium / sparse
```

### Layer 7 — Accessibility Signals

```
Text contrast:            appears WCAG AA / appears low / unknown
Accent contrast:          appears WCAG AA / appears low / unknown
Focus rings:              visible / not visible / not tested
Touch targets (44px+):    appear adequate / appear small / unknown
Line length:              too long / appropriate / short
Line height:              tight / comfortable / spacious
```

---

## Phase 4 — Infer Design Principles

From everything extracted, state 3–5 principles the reference appears to follow.
These are the "why" behind the visual decisions — not descriptions of what you saw.

Format:
```
1. [Principle name]: [one sentence — how the UI demonstrates this]
2. [Principle name]: [one sentence]
```

Example:
```
1. Weight over size: Information hierarchy is expressed through font weight variation
   more than size changes.
2. Restraint as signal: Low component density communicates premium positioning
   rather than filling space to demonstrate value.
```

---

## Phase 5 — Identify the Creative Core

State the single most memorable, distinctive, or bold design decision in this reference.
This is the creative core. It carries forward into the skill and must be preserved in
any UI built from this extraction.

One sentence. Specific. Not "clean design" or "good typography."

---

## Phase 6 — Produce Outputs

1. Design Extraction Summary (the paragraph from Phase 2)
2. Full design system spec — every token filled, using the schema in `references/design-tokens.md`
3. Component inventory — using the format in `references/component-index.md`
4. Design principles list (from Phase 4)
5. Creative core statement (from Phase 5)
6. Confidence log — list every `[inferred]` value in one place at the end

Hand off to Step 3 of the main pipeline.
