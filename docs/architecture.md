# Portfolio System Architecture

> **Repository:** brandonbellsystems.com  
> **Format:** Single-file HTML · Zero Dependencies  
> **Status:** Production · Live

---

## 1. Architectural Philosophy

This portfolio is engineered as a **sovereign single-file runtime**. Every layer — animation, layout, accessibility, security, interaction — is implemented without external dependencies to prove that the same architectural discipline applied to CSI Pro extends to presentation-layer systems.

### The Self-Imposed Constraint

The entire system must ship as one file, open in any browser, and function identically today and in 10 years. This constraint forces intentionality:

- **No bundler fragility** — no `node_modules` rot, no deprecated CLI tools
- **No CDN outages** — no external scripts to fail
- **Instant auditability** — view-source is the documentation

---

## 2. The 24-Category System

The CSS is organized into 24 discrete functional categories. This is not semantic grouping for readability alone; it is a dependency graph where lower categories provide primitives to higher categories.

00 Ambient Atmosphere → 01 Design Tokens → 02 Reset/Base
↓
03 Accessibility → 04 Layout → 05 Animation
↓
06 Typography → 07 Buttons → 08 Badges → 09 Header
↓
10 Rail Nav → 11 Hero → 12 About → 13 Case Cards
↓
14 Services → 15 Philosophy → 16 Employers → 17 CSI Pro Spotlight
↓
18 FAQ → 19 Research → 20 CTA → 21 Footer
↓
22 Utility Shell → 23 Print → 24 Security/Polish


### Notable Subsystems

**Ambient Atmosphere (Category 00)**
The background uses pure CSS fixed-position radial gradients with blur filters and keyframe animation. No canvas. No WebGL. No library.

**Scroll Reveal Engine (Category 05 + JS)**
IntersectionObserver with `threshold: 0.05` and `rootMargin: 80px` bottom buffer. Elements fade up using a cubic-bezier spring curve (`0.16, 1, 0.3, 1`) over 800ms. Staggered delays applied via `data-delay` attributes.

**Mouse-Tracking 3D Tilt (Category 13)**
CSS custom properties (`--mouse-x`, `--mouse-y`, `--rotate-x`, `--rotate-y`) are updated via JavaScript on `mousemove`. The card transforms using `perspective(1000px)` with computed rotation values. Glow effects use radial gradients positioned at the mouse coordinates.

**Structural Wrapper Separation (Category 13 + 15)**
Scroll-reveal animation and hover-tilt physics are on separate DOM nodes to prevent CSS `transition` shorthand cascade collisions. `.animate-on-scroll` sits on a wrapper; `.case-card` sits on the child. This preserves independent transition timing.

---

## 3. Design Rationale

### Why Zero Dependencies?

A portfolio that claims to build sovereign single-file tools must itself be one. Using React or a CSS framework would introduce a contradiction between the claim and the container.

### Why 24 Categories?

The number is arbitrary. The boundary discipline is not. Each category owns a single concern. When a hiring manager asks "how did you structure the CSS?" the answer is not "it was messy but worked" — it is a taxonomy.

### Why IntersectionObserver Over Scroll Events?

`scroll` events fire on the main thread and trigger layout thrashing. IntersectionObserver is asynchronous, batched, and decoupled from the render loop. It is the correct API for reveal animations.

### Why Mouse Tracking on CSS Custom Properties Instead of React State?

Updating React state (or any VDOM) on every `mousemove` would force re-renders at 60–120fps. Writing to CSS custom properties updates the compositor layer directly — no layout, no paint, no JavaScript engine pressure.

---

## 4. Engineering Trade-offs

| Decision | Trade-off | Rationale |
|:---|:---|:---|
| Single-file deployment | No code splitting; larger initial transfer | Guarantees the file is self-contained and future-proof |
| No build tools | No minification pipeline in repo | Honest representation of the artifact; Netlify handles compression |
| IntersectionObserver scroll reveal | No fine-grained parallax | Parallax is aesthetic debt; reveal is sufficient |
| CSS-only ambient orbs | Less dynamic than canvas | Canvas requires JS runtime and blocks accessibility tree |
| Netlify Forms | Third-party form handling | Acceptable boundary — no persistent backend under my control |
