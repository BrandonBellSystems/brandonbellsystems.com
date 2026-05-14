# brandonbellsystems.com

[![Status](https://img.shields.io/badge/status-shipped-22c55e?style=flat-square&labelColor=0f1115)](https://brandonbellsystems.com)
[![Architecture](https://img.shields.io/badge/architecture-24--category-3b82f6?style=flat-square&labelColor=0f1115)](docs/architecture.md)
[![Accessibility](https://img.shields.io/badge/accessibility-WCAG%202.1%20AA-3b82f6?style=flat-square&labelColor=0f1115)](docs/accessibility.md)
[![Dependencies](https://img.shields.io/badge/dependencies-zero-a855f7?style=flat-square&labelColor=0f1115)](docs/architecture.md)
[![Security](https://img.shields.io/badge/security-CSP%20enforced-ef4444?style=flat-square&labelColor=0f1115)](docs/security.md)

> **Production-grade portfolio. Single-file deployment. Zero runtime dependencies.**
> 
> The architecture is the proof.

**[🌐 Live Site](https://brandonbellsystems.com)** ·
**[📄 View Résumé](assets/resume.pdf)** ·
**[🏗 Architecture Deep Dive](docs/architecture.md)**

---

## The System

This repository contains my production portfolio — designed as a **sovereign single-file application** using a 24-category CSS architecture. It is the container that hosts the evidence of six shipped tools, and it is itself a seventh artifact.

### Design Constraints (Self-Imposed)

| Constraint | Implementation |
|:---|:---|
| **Zero dependencies** | No React, no npm, no CDN scripts, no build step |
| **Single-file deployment** | One HTML file containing all markup, styles, and logic |
| **Privacy-native** | No analytics, no cookies, no tracking, no third-party data exfiltration |
| **Accessible by default** | WCAG 2.1 AA — keyboard navigation, ARIA, screen reader support, reduced motion |
| **Secure by default** | CSP headers, no inline script injection vectors, honeypot form protection |
| **Ambient atmosphere** | CSS-only ambient orbs via radial-gradient + blur + keyframe animation |

---

## 24-Category Architecture

| Category | System | Responsibility |
|:---|:---|:---|
| 00 | Ambient Atmosphere | CSS-only orbs (no canvas, no WebGL) |
| 01 | Design Token System | CSS custom properties for theming |
| 02 | CSS Reset + Base Styles | Cross-browser normalization |
| 03 | Accessibility Utilities | sr-only, skip-link, focus-visible, forced-colors |
| 04 | Layout System | Container, section spacing, responsive grid |
| 05 | Animation Keyframes | fadeInUp, shimmer, gradientFlow, pulseGlow |
| 06 | Typography Scale | clamp-based responsive type system |
| 07 | Button System | Tactile physics with rim-highlight glow |
| 08 | Badge Hierarchy | Shipped / Pro / OSS / Available / Coming Soon |
| 09 | Sticky Navigation | backdrop-filter blur, scroll state-transition |
| 10 | Floating Rail Nav | Section-spy dot navigation |
| 11 | Hero System | Grid dot pattern, audience router, IDE preview window |
| 12 | About Section | Photo treatment, badge stack |
| 13 | Case Study Cards | Mouse-tracking glow + 3D tilt physics |
| 14 | Services Matrix | Flagship + supplemental tiers, process steps |
| 15 | Philosophy Spec Cards | Principle-driven proof points |
| 16 | For Employers Section | Résumé CTAs, qualification bullets |
| 17 | CSI Pro Spotlight | Flagship product highlight band |
| 18 | FAQ Accordion | Keyboard-navigable roving-focus accordion |
| 19 | Research Placeholder | Reserved for academic/trade publication |
| 20 | Conversion CTA Band | Audience-segmented path selection |
| 21 | Footer | Identity lattice, source link, social graph |
| 22 | Utility Shell | Toast, offline indicator, back-to-top |
| 23 | Print Styles | Résumé-quality print output |
| 24 | Security + Polish | Safe-area insets, honeypot fields |

> **Full layer-by-layer breakdown:** [docs/architecture.md](docs/architecture.md)

---

## Technical Specifications

| Category | Implementation |
|:---|:---|
| **Format** | Single-file HTML application |
| **Dependencies** | Zero runtime dependencies |
| **Styling** | Vanilla CSS (24-category architecture) |
| **Animation** | CSS keyframes + IntersectionObserver (scroll reveal) |
| **Interaction** | Native JavaScript (vanilla DOM APIs) |
| **Accessibility** | WCAG 2.1 AA |
| **Security** | CSP meta header, XSS-sanitized dynamic content |
| **Hosting** | Static (Netlify) |
| **Form Handling** | Netlify Forms (serverless, no backend maintained) |

---

## Security & Privacy

- **No analytics.** No Google Analytics, no Plausible, no tracking pixels.
- **No cookies.** No consent banners required.
- **No third-party scripts.** The CSP enforces `'self'` for scripts and styles.
- **Form data via Netlify.** Contact form submissions route through Netlify's managed form handler — no custom server, no database under my control.

Full threat model and CSP breakdown: [docs/security.md](docs/security.md)

---

## Accessibility

Engineered to WCAG 2.1 AA from layer zero:

- Skip-link for keyboard users
- ARIA live regions for toast notifications
- Roving focus management in FAQ accordion
- `prefers-reduced-motion` respected globally
- Color-blind safe indicators
- Semantic HTML5 landmark regions

Full audit trail: [docs/accessibility.md](docs/accessibility.md)

---

## Documentation

| Document | Contents |
|:---|:---|
| **[Architecture](docs/architecture.md)** | 24-category system, design rationale, scroll-engine physics, mouse-tracking implementation |
| **[Security](docs/security.md)** | CSP policy, threat model, zero-dependency boundary, form handling |
| **[Accessibility](docs/accessibility.md)** | WCAG 2.1 AA implementation, keyboard navigation, ARIA usage, reduced motion |
| **[Changelog](docs/changelog.md)** | Version history |

---

## Ecosystem Links

- **Live Site:** https://brandonbellsystems.com
- **CSI Pro:** https://customersuccessintelligence.com
- **LinkedIn:** https://www.linkedin.com/in/brandon-bell
- **GitHub:** https://github.com/BrandonBellSystems

---

*Built with the conviction that a portfolio should be as architecturally defensible as the products it describes.*
