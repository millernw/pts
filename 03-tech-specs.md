# 03 — Technical Specs

> Use this file when scaffolding the project, setting up integrations, or making architecture decisions.
> Paste this alongside 00-master-prompt.md at the start of any technical build session.

**Status:** the brand, copy, and structure for this project are settled. **The technical stack is not.** Everything marked **[confirm]** below is a default assumption chosen to fit the brand guide's constraints, not a decision Nate has made. Resolve the Decisions Needed list at the bottom before the first build session.

---

## Framework & Output

- **Framework:** Static HTML/CSS/JS, no build step **[confirm]**
- **Output format:** Multi-page static site — one HTML file per route **[confirm]**
- **CSS approach:** One shared `styles.css` with CSS custom properties for the color and spacing tokens in 02-design-direction.md **[confirm]**
- **JavaScript approach:** Vanilla JS, kept minimal — sticky header state, mobile nav toggle, scroll reveal, accordion **[confirm]**
- **Package manager:** None **[confirm]**

**Why this default:** the brand guide targets sub-2-second mobile loads with two font families and SVG logos, and the site is a 10-page brochure with no app behavior. A static build hits that target with no toolchain. If a CMS is wanted for the blog later (see below), Astro is the natural upgrade path — it keeps the static output and adds Markdown content collections.

**Build sequence:** follow the homepage section order in 04-structure.md. Build one section at a time, review, then move on. Do not generate the whole page in one pass.

---

## Working With AI Studio

This repo exists so that AI Studio (and any other AI builder) can read the brief directly from GitHub rather than having it pasted in.

- **Repo:** `https://github.com/millernw/pts`
- **Repo visibility:** must be **public** for raw asset URLs to resolve and for AI Studio to read the files **[confirm — the client is not confidential, but this is Nate's call]**
- **Raw file URL pattern:** `https://raw.githubusercontent.com/millernw/pts/main/<file>`
- **Reference assets by raw URL, never by pasting the image into a prompt.** Example: `https://raw.githubusercontent.com/millernw/pts/main/assets/pinnacle-logo-horizontal-color.svg`
- Always paste or point at `00-master-prompt.md` first in any session. See `INSTRUCTIONS.md` for which files to combine for which kind of build.

---

## Assets Still To Commit

The build cannot start properly until these are in `/assets/`:

- [x] All logo SVG variants, exported from the Pinnacle Figma file — 11 files, see `assets/README.md` for provenance and three caveats
- [x] `pinnacle-app-icon.svg` for the favicon
- [ ] **Human check:** `pinnacle-logo-horizontal-reversed.svg` was derived by recoloring the wordmark, not exported — no such lockup exists in Figma
- [ ] Jeremy on site with a client — hero photo, cut out, B&W
- [ ] Jeremy Nelson founder portrait — cut out, B&W
- [ ] Team headshot cutouts with names and titles
- [ ] Office team at work, and church/nonprofit staff — "Who we serve" card photos
- [ ] Client logos for the proof strip, once permission is granted

Compress every photo before committing — target under 400kb for a hero image, WebP preferred. See `assets/hero-photo.jpg.txt` for the full workflow.

---

## Hosting & Deployment

- **Hosting target:** Cloudflare Pages or Netlify — both give free static hosting with form handling and a global CDN **[confirm]**
- **Custom domain:** `pinnacletechnology.solutions` appears to be the domain, inferred from the footer email address `info@pinnacletechnology.solutions` **[confirm — including whether there is an existing site at this domain to replace, and whether its rankings need preserving]**
- **Environment:** Static only, plus whatever the form handler and the security assessment require

---

## Integrations

| Integration | Purpose | Notes |
|-------------|---------|-------|
| Booking tool | Book an IT Walkthrough | **[not chosen]** — Calendly or Cal.com. Decide whether the primary CTA opens a booker or a short form that Jeremy calls back from. This is the most consequential open decision on the site. |
| Security assessment | The transitional CTA — collects email, returns a score, lists actions | **[not chosen]** — may be a third-party quiz tool, a vendor-provided assessment, or custom. Drives a follow-up email sequence. See Decisions Needed #2. |
| Form handling | Contact form, and the walkthrough form if used | **[not chosen]** — Cloudflare/Netlify native forms if hosted there, otherwise Formspree |
| Email automation | Assessment follow-up sequence | **[not chosen]** — depends on the assessment tool |
| Google Analytics 4 | Traffic and conversion tracking | **[Measurement ID needed]** |
| Google Business Profile | Local SEO, review badge in footer | Link once reviews are collected |
| Call tracking | Attribute phone calls to the site | **[optional — recommended for this category, but adds a tracking number that may conflict with the "one number to call" promise]** |

> **Industry note:** for local home-services-style businesses like this, local SEO and Google Business Profile optimization typically drive more inbound than site design does. Service-area pages per town are a strong P2 play once the launch pages are live.

---

## Forms & Data Collection

| Form | Fields | Where Data Goes | Notes |
|------|--------|----------------|-------|
| Contact | Name, Organization, Email, Phone, Message | **[destination needed]** | Labels always visible above fields, 48px tall inputs, 2px orange focus ring |
| Book a walkthrough | **[depends on booking tool]** | **[destination needed]** | If a booker is embedded, no form is needed |
| Security assessment | Email + assessment answers | **[depends on assessment tool]** | Must state what happens to the email before submit |

Every form needs a visible privacy line and a real success state. No form may collect more than it needs.

---

## Authentication

- **Auth needed:** No. There is no client portal at launch.
- If a client portal is added later it is a separate project, not a page on this site.

---

## CMS & Content Management

- **CMS needed:** Not at launch **[confirm]**
- **Who updates content:** Nate, for now
- **CMS preference:** Markdown files if a blog is added at P2. A full CMS is not justified for 10 static pages.
- **Content types that would need it:** blog posts, testimonials, team members
- **Localization:** No

---

## Performance & SEO

- **SEO priority:** Important — local search is a primary acquisition channel for this category
- **Core Web Vitals target:** LCP under 2.0s on mobile, per the brand guide
- **Lighthouse score goal:** 90+
- **Image optimization:** manual — WebP, compressed before commit, explicit `width`/`height` to avoid layout shift
- **Sitemap needed:** Yes
- **Robots.txt needed:** Yes
- **Structured data:** `LocalBusiness` on the homepage with NAP and hours; `FAQPage` on the homepage FAQ; `Service` on each of the four service pages
- **NAP consistency:** Pinnacle Technology Solutions · 3249 N. Anthony Blvd., Fort Wayne, IN 46805 · (260) 205-8900 · Mon–Fri 8:00–5:00. Identical in the footer of every page and in the structured data.

---

## Browser & Device Support

- **Minimum browser support:** last 2 versions of Chrome, Firefox, Safari, Edge
- **Accessibility target:** **WCAG AA, non-negotiable.** The brand guide states that if a brand rule and a contrast rule conflict, the contrast rule wins. Specifically:
  - Charcoal text on orange buttons, never white
  - Steel Gray for captions only, never paragraphs
  - Orange `#F79862` is never used for meaningful text or icons on white
  - Real `<button>`, `<a href>`, `<input>` + `<label>` elements — never a clickable `div`
  - `aria-label` on icon-only buttons; decorative SVG gets `aria-hidden="true"`
  - Visible focus states on everything interactive
  - Respect `prefers-reduced-motion`

> *Responsive breakpoints and layout behavior: see **04-structure.md**.*

---

## Known Constraints

- Two font families maximum — Outfit and Inter, only the weights listed in 02-design-direction.md
- The logo must be placed as an SVG file, never rendered as live text
- No gradients except on shard graphics
- Core content must be readable without JavaScript — JS is progressive enhancement only
- No paid npm packages
- Sub-2-second mobile load is a hard target, not an aspiration — it constrains how many photos go above the fold

---

## Decisions Needed Before Building

1. **Framework and hosting.** Everything above marked [confirm]. A static build is assumed.
2. **The security assessment.** This is the transitional CTA, it appears in the nav on every page, it has its own results page with the primary CTA on it, and it drives an email sequence. It needs a tool, a URL, a known duration, and a follow-up sequence before the lead-generator band can be built for real.
3. **Booking flow.** Does "Book an IT Walkthrough" open an embedded booker, go to a form, or go to a `tel:` link? This changes the hero, the plan section, the final CTA, and the assessment results page.
4. **Repo visibility.** Public is assumed so raw asset URLs work.
5. **Domain and existing site.** Confirm the domain, and whether an existing site is being replaced — if so, audit its rankings and set up redirects before launch.
6. **Analytics and call tracking.** GA4 property, and whether to add call tracking despite the tracking-number tension.
