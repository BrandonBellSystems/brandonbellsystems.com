# Portfolio Accessibility Implementation

> **Standard:** WCAG 2.1 AA  
> **Approach:** Architected from layer zero, not retrofitted

---

## 1. Keyboard Navigation

| Feature | Implementation |
|:---|:---|
| Skip link | Visible on `:focus`, jumps to `#main` |
| FAQ accordion | Roving `tabindex` with Arrow keys |
| Modal dialog | Focus trap, Escape to close, restore focus on exit |
| Buttons | All interactive elements reachable via Tab |

## 2. Screen Reader Support

- ARIA live region for toast notifications (`aria-live="polite"`)
- Accordion triggers explicitly control panels (`aria-expanded`, `aria-labelledby`)
- Hidden decorative elements (`aria-hidden="true"`)
- Alternative text for headshot image

## 3. Motion & Visual

- `prefers-reduced-motion: reduce` disables all animations via `!important` reset
- Color-blind safe indicators
- Minimum contrast ratios met for all text pairs
- Focus-visible outlines (`2px solid var(--accent)`) for keyboard users

## 4. Structural

- Semantic HTML5 elements: `<header>`, `<main>`, `<section>`, `<footer>`, `<nav>`
- Logical heading hierarchy (`h1` → `h2` → `h3`)
- No carousel or auto-rotating content
