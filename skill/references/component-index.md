# Component Index

Document every component for this design system.
Populated after the design system spec is finalized.

---

## Format

```
### ComponentName
Purpose: what it does, when to use it
Variants: list each with a visual description
Sizes: which sizes apply
States: which states are implemented
Tokens: which token variables govern its appearance
Rules: when to use which variant
Anti-patterns: what not to do
```

---

## Components

### Button
Purpose:
Variants: primary / secondary / ghost / destructive / link
Sizes: sm / md / lg
States: default / hover / active / focus / disabled / loading
Tokens: --color-accent, --color-text-inverse, --radius-btn, --spacing-*, --transition-default
Rules:
Anti-patterns:

---

### Input
Purpose:
Variants: default / error / success / disabled
Label: top / floating / inline
States: default / focus / error / success / disabled
Tokens: --color-surface, --color-border, --color-border-focus, --radius-input
Rules:
Anti-patterns:

---

### Card
Purpose:
Variants: default / outlined / elevated / flat
States: default / hover (interactive cards only)
Tokens: --color-surface, --color-border, --radius-card, --shadow-card, --spacing-*
Rules:
Anti-patterns:

---

### Badge
Purpose:
Variants: default / success / warning / danger / info
Styles: filled / outlined / subtle
Tokens: --color-*-subtle, --color-*, --radius-pill
Rules:
Anti-patterns:

---

### Navigation
Type: [topbar / sidebar / bottom / none]
Active state:
Mobile behavior:
Tokens:
Rules:
Anti-patterns:

---

### Modal
Sizes: sm / md / lg / full
Structure: header / body / footer
Overlay:
Entry animation:
Tokens:
Rules:
Anti-patterns:

---

### Table
Variants: default / striped / compact
Features: sortable / hoverable / paginated
Tokens:
Rules:
Anti-patterns:

---

### Toast / Notification
Variants: success / error / warning / info
Position:
Dismiss: auto / manual
Tokens:
Rules:
Anti-patterns:

---

### Empty State
Structure: icon + heading + description + CTA
Tone:
Tokens:
Rules:
Anti-patterns:

---

### Loading States
Spinner: [when]
Skeleton: [when — preferred for content]
Progress bar: [when]
Tokens:
Rules:
Anti-patterns:

---

## Cross-Component Rules
- [Add project-specific relationships between components here]
