# Design Tokens

Full token schema. Populated after extraction or ideation is complete.
Every token must have a real value before the skill is packaged.
Mark inferences: `/* [inferred] */`. Mark unknowns: `/* [TBD — reason] */`.

---

```css
:root {

  /* ── COLOR: Backgrounds ── */
  --color-bg:                  ;
  --color-surface:             ;
  --color-surface-raised:      ;
  --color-surface-overlay:     ;

  /* ── COLOR: Text ── */
  --color-text:                ;
  --color-text-muted:          ;
  --color-text-disabled:       ;
  --color-text-inverse:        ;

  /* ── COLOR: Accent ── */
  --color-accent:              ;
  --color-accent-hover:        ;
  --color-accent-active:       ;
  --color-accent-subtle:       ;
  --color-text-accent:         ;

  /* ── COLOR: Borders ── */
  --color-border:              ;
  --color-border-strong:       ;
  --color-border-focus:        ;

  /* ── COLOR: Semantic ── */
  --color-danger:              ;
  --color-danger-subtle:       ;
  --color-success:             ;
  --color-success-subtle:      ;
  --color-warning:             ;
  --color-warning-subtle:      ;
  --color-info:                ;
  --color-info-subtle:         ;

  /* ── TYPOGRAPHY ── */
  --font-heading:              ; /* family, fallback */
  --font-body:                 ; /* family, fallback */
  --font-mono:                 ; /* family, fallback */

  /* ── FONT SIZES ── */
  --text-xs:    0.75rem;
  --text-sm:    0.875rem;
  --text-base:  1rem;
  --text-lg:    1.125rem;
  --text-xl:    1.25rem;
  --text-2xl:   1.5rem;
  --text-3xl:   1.875rem;
  --text-4xl:   2.25rem;
  --text-5xl:   3rem;

  /* ── FONT WEIGHTS ── */
  --weight-regular:   400;
  --weight-medium:    500;
  --weight-semibold:  600;
  --weight-bold:      700;
  --weight-black:     900;

  /* ── LINE HEIGHTS ── */
  --leading-tight:    1.2;
  --leading-snug:     1.375;
  --leading-normal:   1.5;
  --leading-relaxed:  1.625;

  /* ── LETTER SPACING ── */
  --tracking-tight:   -0.04em;
  --tracking-snug:    -0.02em;
  --tracking-normal:   0;
  --tracking-wide:     0.04em;
  --tracking-caps:     0.1em;

  /* ── SPACING ── */
  --spacing-1:   4px;
  --spacing-2:   8px;
  --spacing-3:   12px;
  --spacing-4:   16px;
  --spacing-5:   20px;
  --spacing-6:   24px;
  --spacing-8:   32px;
  --spacing-10:  40px;
  --spacing-12:  48px;
  --spacing-16:  64px;
  --spacing-20:  80px;
  --spacing-24:  96px;

  /* ── BORDER RADIUS ── */
  --radius-none:   0;
  --radius-sm:              ;
  --radius-md:              ;
  --radius-lg:              ;
  --radius-card:            ;
  --radius-btn:             ;
  --radius-input:           ;
  --radius-pill:   9999px;

  /* ── SHADOWS ── */
  --shadow-sm:              ;
  --shadow-card:            ;
  --shadow-lg:              ;
  --shadow-overlay:         ;

  /* ── MOTION ── */
  --duration-fast:     100ms;
  --duration-default:  150ms;
  --duration-slow:     300ms;
  --easing-default:    ease;
  --easing-out:        ease-out;
  --easing-spring:     cubic-bezier(0.34, 1.56, 0.64, 1);

  /* ── LAYOUT ── */
  --container-max:          ;
  --nav-height:             ;
  --sidebar-width:          ;
  --sidebar-collapsed:      ;

  /* ── Z-INDEX ── */
  --z-base:      0;
  --z-raised:    10;
  --z-dropdown:  100;
  --z-sticky:    200;
  --z-overlay:   300;
  --z-modal:     400;
  --z-toast:     500;
}
```

---

## Confidence Log

| Token | Value | Confidence | Note |
|---|---|---|---|
| | | observed / inferred | |

---

## Source
- Extracted from: [URL / screenshot / concept name]
- Mode: extraction / ideation / hybrid
