# 00 — Master Prompt
> Paste this entire file at the start of every AI coding session.
> Keep this under one page. Detail lives in files 01–04.

---

## Project Identity

- **Project name:** Pinnacle Technology Solutions (short form: Pinnacle)
- **Tagline / one-liner:** All your tech. One call.
- **Project type:** Service business site (local managed IT provider)
- **Primary goal:** Get a qualified local business or nonprofit to book an on-site IT walkthrough
- **Success metric:** Booked walkthroughs per month, plus email captures from the free security assessment

---

## Audience

- **Primary user:** A business manager — owner, CFO, or operations manager — at a 10–80 person company in northeast Indiana. Sharp and capable at their actual job, but became the de facto IT person by default. *(Brand guide names 10–20 employees as the sweet spot; see Open Conflicts in 01-content.md.)*
- **Their core problem:** They are managing a loose tangle of vendors for network, phones, email, cyber security, cameras and door locks. None of it talks to each other, and when something breaks nobody answers.
- **Secondary audience:** Nonprofits and ministries — churches, schools, charities — on tight budgets with volunteer turnover and donor data to protect.
- **Device context:** Both. Desktop during the workday, mobile for referral click-throughs.
- **Tech literacy:** Deliberately assume **non-technical**. If a sentence needs IT jargon to make sense, rewrite it.

---

## Design & Tech

> Full design specs: see **02-design-direction.md**
> Full tech specs: see **03-tech-specs.md**

Signature look in one line: mostly white pages, Pinnacle Orange and Deep Teal as the core pair, sharp 0–4px corners, diagonal shards from the logo mark, and black-and-white cutout photos of the real Pinnacle team.

---

## Assets

- **Logo:** `/assets/` — place as SVG, never retyped as live text. Variants: `pinnacle-logo-horizontal-color.svg` (default, light backgrounds), `-reversed.svg` (on Deep Teal / charcoal), `-white.svg` (over photos), `-black.svg`, `-orange.svg` (dark only), `pinnacle-mark-orange.svg`, `pinnacle-app-icon.svg` (favicon), plus stacked lockups. **All 11 files are in `/assets/` — see `assets/README.md` before using them.**
- **Hero image:** Photo of Jeremy on site with a client. **[not shot yet — see 02 for treatment]**
- **Brand colors file:** See the full token table in **02-design-direction.md**

---

## Ground Rules for This Project

> These apply to every prompt in this project. Never violate these.

- DO use only the colors, logo files, and fonts in 02-design-direction.md. Do not invent accent colors or substitute fonts.
- DO place the logo as an SVG file. **Never retype "pinnacle" as live text to fake the logo.**
- DO let accessibility win ties. If a brand rule and a contrast rule conflict, follow the contrast rule.
- DO use orange buttons with **charcoal** text. White text on orange fails contrast — it is the single most common mistake on this project.
- DO write for a non-technical small business owner. Spell out acronyms on first use, or avoid them (MSP, RMM, EDR rarely belong on this site).
- DO write real copy from 01-content.md — no Lorem Ipsum, ever.
- DO keep clearly labeled placeholders for anything in brackets. **Never invent statistics, testimonials, client names, or logos.**
- DO name the local service area: Fort Wayne and northeast Indiana. Never "nationwide."
- DO make it mobile-first and fully responsive.
- DO NOT add sections, pages, or features not explicitly requested.
- DO NOT use navy or bright blue as a main color — that is the generic MSP look this brand is avoiding.
- DO NOT use pill buttons, large rounded cards, or glassmorphism. The logo is all sharp angles.
- DO NOT use banned imagery: glowing circuit boards, binary code, padlock-on-blue icons, hooded hackers, handshake stock photos, or server rooms that are not Pinnacle's.
- DO NOT use fear tactics in body copy. *(The one sanctioned exception is the lead-generator headline — see 01-content.md.)*
- Output format: **[confirm — default assumption is a static multi-page build, see 03-tech-specs.md]**

---

## Working Preferences

- Confirm your interpretation before generating if anything is ambiguous
- Build one section or component at a time unless told otherwise
- The homepage section order in 04-structure.md is already in conversion order — use it as the build sequence
