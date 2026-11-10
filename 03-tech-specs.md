# 03 — Technical Specs

> Use this file when scaffolding the project, setting up integrations, or making architecture decisions.
> Paste this alongside 00-master-prompt.md at the start of any technical build session.

**Status:** the brand, copy, and structure for this project are settled. **The technical stack is not.** Everything marked **[confirm]** below is a default assumption chosen to fit the brand guide's constraints, not a decision Nate has made. Resolve the Decisions Needed list at the bottom before the first build session.

---

## Framework & Output

- **Framework:** React + Vite
- **Output format:** Multi-page site using React Router — one route per page in the site map
- **CSS approach:** Tailwind, with the 02-design-direction.md palette and spacing scale defined as theme tokens in `tailwind.config.js`. No arbitrary hex values in components — use the token names
- **JavaScript approach:** TypeScript
- **Package manager:** npm

**Why this stack:** the site is being built in Google AI Studio, whose build mode produces React + Tailwind projects. An earlier draft of this file specified static HTML with no build step, chosen to hit the sub-2-second mobile target. That target is still reachable through a Vite production build, and fighting the tool's natural output costs more than it saves. **If the build moves off AI Studio, static HTML or Astro is the better fit — revert this section.**

**Token discipline matters more than the framework.** The colors, spacing scale, and type scale in 02-design-direction.md must live in `tailwind.config.js` as named tokens. If components carry raw hex values, the contrast rules stop being enforceable and the palette drifts within two sessions.

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
- [ ] **Sign-off:** `pinnacle-logo-horizontal-reversed.svg` was derived by recoloring the wordmark, not exported — no such lockup exists in Figma. Renders correctly on Deep Teal, but it is not official artwork
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
| Security assessment | The transitional CTA | **Pinnacle's own existing system.** Do not build one. The band and nav item link out to it. **[URL needed]** — the build uses the placeholder `#assessment-url-tbd`. |
| Form handling | Contact form | **Connected** — HighLevel form tracking in the Pinnacle sub-account. Submissions create contacts. |
| Email automation | Follow-up on contact submissions | **[not chosen]** — HighLevel workflows are the obvious route since contacts already land there |
| Google Analytics 4 | Traffic and conversion tracking | **[Measurement ID needed]** |
| Google Business Profile | Local SEO, review badge in footer | Link once reviews are collected |
| Call tracking | Attribute phone calls to the site | **[optional — recommended for this category, but adds a tracking number that may conflict with the "one number to call" promise]** |

> **Industry note:** for local home-services-style businesses like this, local SEO and Google Business Profile optimization typically drive more inbound than site design does. Service-area pages per town are a strong P2 play once the launch pages are live.

---

## Forms & Data Collection

| Form | Fields | Where Data Goes | Notes |
|------|--------|----------------|-------|
| Contact | Name, Organization, Email, Phone, Message | HighLevel CRM, via connected form tracking | Labels always visible above fields, 48px tall inputs, 2px orange focus ring. Built and wired. |
| Book a walkthrough | **[depends on booking decision]** | **[destination needed]** | If a booker is embedded, no form is needed |
| Security assessment | Handled entirely by Pinnacle's own system | Not this site | The site only links out |

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

1. ~~**Framework and hosting.**~~ **Resolved for the build** — React + Tailwind, built in HighLevel AI Studio. Hosting is whatever AI Studio publishes to; confirm the custom domain before launch.
2. ~~**The security assessment.**~~ **Resolved** — Pinnacle has its own system. The site links out. **Still needed: the URL and how long it takes.**
3. **Booking flow — still open.** Does "Book an IT Walkthrough" open an embedded booker, go to a form, or go to a `tel:` link? It appears in the header, hero, plan, and final CTA.
4. ~~**Repo visibility.**~~ **Resolved** — public, verified by unauthenticated fetches of the raw asset URLs.
5. **Domain and existing site — still open.** Confirm the domain, and whether an existing site is being replaced. If so, audit its rankings and set up redirects before launch.
6. **Analytics and call tracking — still open.** GA4 property, and whether to add call tracking despite the tracking-number tension.
7. **Photography — the real blocker.** Hero, Jeremy, team headshots, and the two "Who we serve" shots. Every one is a labelled placeholder until the shoot happens.
