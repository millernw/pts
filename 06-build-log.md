# 06 — Build Log

> What actually got built, where it lives, and what is still a placeholder.
> Files 00–04 are the brief. This file is the record of the build, so the two don't drift apart.

**Last updated:** 10 Nov 2026

> **Note on identifiers:** this repository is public, so it deliberately contains no HighLevel sub-account IDs, project IDs, or internal console URLs. To find the build: HighLevel → **Pinnacle Technology Solutions** sub-account → **AI** → **AI Studio**.

---

## Where the site lives

Built in **HighLevel's AI Studio** (the `/vibe` builder inside the Pinnacle sub-account), not Google AI Studio. The project is named **"Pinnacle Managed IT"** — auto-generated from the first prompt, so rename it if that bothers you.

Output is a **React + Tailwind** app. That is why `03-tech-specs.md` specifies React rather than the static HTML originally planned: AI Studio's build mode emits React, and fighting the tool costs more than it saves.

**The site is not published.** Everything below exists in preview only.

---

## Brand Board — set up before the build

AI Studio reads the sub-account's Brand Board, which was empty. It now holds:

- **Design kit "Pinnacle Technology Solutions"** — 13 colors, each labelled with its *role* rather than just its name (`Charcoal (body text, button text on orange)`, `Steel Gray (captions only, never paragraphs)`), Outfit and Inter with fallbacks, and 5 logos referenced by their raw GitHub URLs from `/assets` in this repo.
- **Brand voice "Pinnacle – StoryBrand"**, set as the sub-account default. Built from the BrandScript: target audience, pain points, brand promise, purpose, competitive advantage, risks of inaction, USP, CTA. The tone field carries the bans explicitly — no fear tactics, no "nationwide", no corporate filler, no invented statistics.

Populating this before prompting mattered more than any single prompt. It is why the output came back on-brand rather than generic.

> **One thing to check:** the design kit shows `isDefault: false` and the API has no field to change it. It is the only kit in the account so AI Studio may use it regardless, but if colors drift, set it as default in the Brand Board UI — one click.

---

## Routes built

All 12 P1 pages exist and are wired. Nav uses dropdowns for Services and Who We Serve.

| Route | Notes |
|-------|-------|
| `/` | The full 12-section homepage |
| `/services` | Hub with the four cards and a CTA band |
| `/managed-it`, `/phones`, `/cyber-security`, `/building-security` | Four service pages from one shared `service-page` component: hero, What's included, the shared three-step How it works, Who this is for, three FAQs, CTA |
| `/businesses`, `/nonprofits` | Audience pages, each with three audience-specific FAQs |
| `/about` | Belief first, then Jeremy, then a four-slot team section |
| `/contact` | Form wired to the CRM, plus NAP and hours |
| `/privacy`, `/terms` | Plain-English drafts, each with a visible `[DRAFT — requires legal review before launch]` banner |

**Deliberately not a page:** the security assessment. Pinnacle has its own system. The nav item and the lead-generator band link out to it via the placeholder `#assessment-url-tbd`.

---

## Integrations live in the sub-account

- **Form tracking is connected.** Contact form submissions create contacts in the Pinnacle sub-account. This was switched on during the build and is a real change to a live account — reversible, but worth knowing.

---

## Design decisions that shipped

These go beyond `02-design-direction.md` and were made during the build:

- **Hero** H1 at `clamp(44px, 6vw, 72px)`, leading ~1.05, with two overlapping shards at different scales, one cropped hard off the right edge.
- **The signature light/bold type move runs through every section heading**, not just the hero — *"One team owns all of it."*, *"…whoever is closest when something breaks."*
- **The Guide section is a full-width Deep Teal band.** This is the single biggest visual improvement: it gives the page a dark anchor mid-scroll instead of only at the lead-gen band and footer.
- **Photo placeholders are designed, not grey boxes** — Warm Light fill, thin orange corner brackets, label centred in Steel Gray small caps. They will be on screen until the shoot, so they had to look intentional.
- **The comparison table earns its contrast** — "Without one team watching" is muted Steel Gray with no fill; "With Pinnacle" sits on a Teal Mist panel with orange markers.
- **Stakes questions are set large**, one per row with orange angled markers, instead of a bulleted list.
- **A `Reveal` component** fades and rises 16px over 280ms, staggered ~60ms within groups, honouring `prefers-reduced-motion`.
- **Vertical rhythm varies** — dark bands breathe, quieter sections tighten — rather than every section being the same 96px block.
- **One invented headline:** the comparison section had no H2 in the copy doc, so the build wrote *"One team watching changes everything."* On-voice, but not from the brief. Approve or replace it.

---

## Still placeholder, still blocked

Nothing below can be solved by another prompt.

- [ ] **Photography.** Hero (Jeremy on site with a client), Jeremy's portrait, team headshots with names and titles, office team, church/nonprofit staff. The whole visual identity is built around B&W cutouts over shards; until these exist the site looks unfinished no matter what.
- [ ] **Assessment URL** from Pinnacle's own system, plus how long it takes, to replace `#assessment-url-tbd` and the `[X] minutes` microcopy.
- [ ] **Booking destination** for "Book an IT Walkthrough" — booker, form, or `tel:`. It appears in four places.
- [ ] **Proof numbers:** average client relationship length, and the dollar figure for recovered licenses.
- [ ] **Three testimonials** with name, title, organization and written permission.
- [ ] **Client logo permissions** for the proof strip.
- [ ] **Service-area town list** for the footer and local SEO.
- [ ] **Legal review** of `/privacy` and `/terms`.
- [ ] Three open copy conflicts in `01-content.md` — client size, the proposal shape, and the lead-gen tone.

---

## Lessons worth keeping

**Populate the Brand Board before prompting.** It did more for output quality than any wording.

**The builder will fake the logo.** It rendered "Pinnacle Technology Solutions" as live title-cased text next to a hand-drawn mark, while the real SVGs sat unused. Always check, and point it at the raw GitHub URLs explicitly.

**Figma exports are not transparent.** Every node export arrived wrapped in a `#F5F5F5` backing rect plus the whole artboard as a white rect. Both were stripped. Unstripped, the white lockup would have been white-on-white.

**Writing instructions leak into copy.** See the checklist item in `05-build-prompts.md`. Read the rendered page, not the brief.

**Build in batches, not all at once.** Quality held across four batches of roughly five pages. Each batch re-read the existing components first, which is slow but kept the design consistent.
