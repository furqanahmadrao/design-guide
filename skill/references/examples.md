# Examples

Quality criteria and output comparisons. Add to this as the project builds.

---

## Quality Checklist

Before presenting any output, verify:

**Tokens**
- [ ] All colors reference CSS variables — no raw hex in component styles
- [ ] All spacing uses the scale — no arbitrary px values
- [ ] All radii, shadows, and transitions use tokens

**Typography**
- [ ] Heading font applied to all headings
- [ ] Type scale applied correctly (H1 > H2 > H3 > body > small)
- [ ] Font smoothing applied

**Visual Identity**
- [ ] Mood matches brand-notes.md
- [ ] Creative core decision is visible and preserved
- [ ] Does not look like generic AI-generated UI

**Components**
- [ ] All interactive states implemented (hover, focus, disabled)
- [ ] No undocumented variants introduced without reason

**Layout**
- [ ] Grid and container rules followed
- [ ] Responsive breakpoints implemented

**Accessibility**
- [ ] Focus rings visible
- [ ] Contrast appears to meet WCAG AA
- [ ] Touch targets adequate on mobile

---

## Strong Outputs

### [Name]
What makes it strong:
- [Specific reason]
- [Creative decision that worked]

---

## Anti-patterns Caught

### Generic AI defaults
Symptoms: common font choices for the category, purple/blue gradient on white, symmetric predictable layout, no hover states, hardcoded colors.
Fix: make one specific creative choice per axis — color, type, layout — that reflects the product identity.

### Spec dump preview
Symptoms: colored squares with labels, no rendered components, no interactivity.
Fix: the preview page must render real components with CSS hover states and style itself using its own token system.

### Empty tokens in packaged skill
Symptoms: reference files have placeholder text like "[value]" or empty declarations.
Fix: every token gets a real value before packaging. TBD tokens get a comment explaining why.
