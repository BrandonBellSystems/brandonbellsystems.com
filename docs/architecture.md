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

