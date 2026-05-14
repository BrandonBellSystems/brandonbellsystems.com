# Portfolio Security Model

> **Status:** Production  
> **Hosting:** Netlify Static

---

## 1. Threat Model

| Threat | Mitigation | Limitation |
|:---|:---|:---|
| XSS via injected content | CSP header restricts script-src to `'self'` and inline hashes | None significant; no user-generated dynamic HTML |
| Data exfiltration | No analytics, no cookies, no tracking scripts | Cannot protect against browser extension data access |
| Form spam | Netlify honeypot field + bot-field detection | Determined actors may bypass |
| Supply chain attack | No npm, no CDN scripts, no external CSS | File size is larger than a bundled equivalent |

---

## 2. Content Security Policy

```http
Content-Security-Policy: default-src 'self'; script-src 'self' 'unsafe-inline' https://gumroad.com; style-src 'self' 'unsafe-inline'; img-src 'self' data: blob: https:; font-src 'self'; connect-src 'self' https://api.github.com; frame-src 'self' https://brandonbellsystems.gumroad.com; object-src 'none'; base-uri 'self'; form-action 'self' https://netlify.com; upgrade-insecure-requests;

* 'unsafe-inline' is required for the single-file architecture
* frame-src allows Gumroad checkout embed
* object-src 'none' prevents plugin injection

3. Privacy Guarantee
* Zero analytics. No visitor tracking.
* Zero cookies. No consent banner required.
* Zero third-party scripts. External resources are user-initiated only.
* Form data. Submissions route through Netlify Forms. I do not operate a server that stores or processes data directly.

4. Form Security
* netlify-honeypot="bot-field" — hidden field that must remain empty
* form-name hidden field for Netlify routing
* autocomplete attributes for user-agent assistance
* required fields enforced at the HTML level


