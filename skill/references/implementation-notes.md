# Implementation Notes

Frontend constraints and developer guidance. Populated after spec is finalized.

---

## Stack

```
Framework:    [HTML/CSS/JS / React / Vue / other]
Styling:      [CSS custom properties / Tailwind / CSS Modules]
Animation:    [CSS transitions / Motion / GSAP]
Icons:        [library name]
Fonts:        [Google Fonts / self-hosted / system]
```

---

## Font Loading

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="[GOOGLE_FONTS_URL]" rel="stylesheet">
```

Always apply:
```css
body { -webkit-font-smoothing: antialiased; -moz-osx-font-smoothing: grayscale; }
```

---

## Token Rules

All values reference CSS custom properties. No raw values in component CSS.

```css
/* WRONG */  .card { border-radius: 12px; background: #1a1a1a; }
/* RIGHT */  .card { border-radius: var(--radius-card); background: var(--color-surface); }
```

---

## Component Rules

- Buttons: always `transition: all var(--duration-default) var(--easing-out)`
- Focus: always `:focus-visible`, never `:focus` alone
- Cards: always `overflow: hidden` with border-radius
- Disabled: always `pointer-events: none; opacity: 0.4`

---

## Responsive

Mobile-first. Base styles = mobile. Min-width media queries for larger breakpoints.

```css
@media (min-width: 768px) { /* tablet+ */ }
@media (min-width: 1024px) { /* desktop+ */ }
```

---

## Accessibility

- Contrast: body text ≥ 4.5:1, large text ≥ 3:1
- Focus rings: 2px, 2px offset, use --color-border-focus
- Touch targets: 44×44px minimum
- Reduced motion: `@media (prefers-reduced-motion: reduce) { * { transition: none !important; } }`
- Semantic HTML: `<button>` for actions, `<a>` for navigation, labels on all inputs

---

## Anti-patterns

- Hardcoded hex values outside `:root`
- Inline styles for layout, color, or spacing
- Arbitrary z-index values outside the token scale
- `!important` outside reset context
