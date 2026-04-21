# Layout Patterns

Grid system, page structures, and composition rules. Populated after spec is finalized.

---

## Grid

```
Columns:        [number]
Gutter:         [value]
Container max:  [value]
Edge padding:   [value]

Breakpoints:
  mobile:   < 768px
  tablet:   768px – 1023px
  desktop:  ≥ 1024px
  wide:     ≥ 1280px
```

---

## Page Structures

### [Primary layout type — e.g. App Shell / Landing / Settings]
Describe: topbar height, sidebar width, content padding, scroll behavior.

### [Secondary layout type if applicable]

---

## Card Grid

```
Desktop:  [n] columns
Tablet:   [n] columns
Mobile:   1 column
Gap:      [value]
Min card width: [value]
```

---

## Section Rhythm

- Vertical spacing between sections: [token]
- Alternating backgrounds: yes / no
- Container behavior: all sections contained / some full-bleed

---

## Navigation Behavior

- Desktop: [describe]
- Tablet: [describe — collapsed / overlay]
- Mobile: [describe — drawer / bottom bar / hamburger]

---

## Anti-patterns

- [Layout decisions that break the system]
- [Responsive behaviors to avoid]
