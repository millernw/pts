# 05 — Build Prompts for AI Studio

> **Status: the site has been built.** See `06-build-log.md` for what exists and where.
> Keep this file for rebuilding, for adding sections, or for starting the next project.
> It was written for Google AI Studio; the site was actually built in **HighLevel's AI Studio**, which reads the sub-account Brand Board. The prompts work in either, but in HighLevel you can lean on the Brand Board instead of restating the palette.

---

## DECIDE FIRST — four things, ten minutes

These are the conflicts recorded in `01-content.md`. **Resolve them before you paste anything.** Each one appears in several places, so deciding afterwards means hunting the same string through five files.

| # | Decision | Options | Where it lands |
|---|----------|---------|----------------|
| 1 | ~~Primary CTA label~~ **SETTLED** | **Book an IT Walkthrough** | Header, hero, plan, final CTA — 4 places in the built site |
| 2 | **Client size** | 10–80 employees (current) / 10–20 | `/businesses` copy, hero subhead tone |
| 3 | **The proposal** | Flat monthly price (current) / Two options + 60–90 day promise | Plan step 2 |
| 4 | **Lead-gen tone** | Keep the "one click from a meltdown" headline (current) / rewrite calm | Lead generator band |

If you keep the current answers, change nothing. If you don't, edit `01-content.md` **first**, then build.

**Also decide:** does the primary CTA open a booking tool, a form, or a `tel:` link? The prompts below assume **a form that routes to a booking page**, and say so. Change that line if you've picked a booker.

---

## How to use these prompts

AI Studio may or may not be able to fetch files from GitHub. Try the fetch version first; if it says it can't, paste the file contents instead.

**Fetch version** — raw URLs:

```
https://raw.githubusercontent.com/millernw/pts/main/00-master-prompt.md
https://raw.githubusercontent.com/millernw/pts/main/01-content.md
https://raw.githubusercontent.com/millernw/pts/main/02-design-direction.md
https://raw.githubusercontent.com/millernw/pts/main/03-tech-specs.md
https://raw.githubusercontent.com/millernw/pts/main/04-structure.md
```

**Build one section at a time.** Pasting everything and asking for the whole site degrades badly around the sixth or seventh section. The section order in `04-structure.md` is your build queue.

---

## Prompt 1 — Scaffold and design tokens

> Paste `00-master-prompt.md` and `03-tech-specs.md` above this.

```
You are building a marketing website for Pinnacle Technology Solutions, a managed IT
company in Fort Wayne, Indiana. The two files above are the project brief. Read them
before writing any code.

For this first step, build ONLY the project scaffold and the design system. Do not
build any page sections yet.

1. Set up a React + Vite + TypeScript project with Tailwind and React Router.

2. In tailwind.config.js, define these as named theme tokens. Use the token names
   everywhere in components — never raw hex values:

   colors:
     orange        #F79862   (primary — buttons, mark, accents)
     ember         #E8834A   (orange hover/pressed)
     orangeText    #B84E14   (orange text and links on white)
     deepTeal      #0E4A55   (dark bands, footer)
     charcoal      #231F20   (body text, dark sections)
     steel         #737373   (captions only, never paragraphs)
     warmLight     #F7F5F2   (alternate section background)
     tealMist      #E3F1EF   (cool alternate section background)
     orangeTint    #FEF0E8   (callout boxes)
     teal          #1F7A7A   (secondary buttons, links on white)
     seaGlass      #5FC4BE   (accents on dark only)
     amber         #F5B841   (badges, ratings on dark)
     border        #E5E5E5
     inputBorder   #BDBDBD
     success       #1E7F5C
     warning       #8A5A00
     error         #B3261E

   spacing scale: 4, 8, 12, 16, 24, 32, 48, 64, 96, 128 px
   borderRadius:  0 and 2px and 4px ONLY — no larger values, no pill, no full

3. Load Outfit (300, 400, 500, 600) and Inter (400, 600) from Google Fonts. Nothing else.
   Set up type scale utilities:
     h1   Outfit 300, 56px/1.1 desktop, 38px mobile
     h2   Outfit 400, 40px/1.15 desktop, 30px mobile
     h3   Outfit 500, 24px/1.3 desktop, 21px mobile
     eyebrow  Inter 600, uppercase, 0.08em tracking, 13px
     body Inter 400, 18px/1.6 desktop, 17px mobile
     small Inter 400, 14px/1.5
     button Inter 600, 16px/1

4. Build these shared components only:
   - Button (primary: orange bg, CHARCOAL text, 14px/28px padding, 2px radius,
     hover bg ember. secondary: transparent, 2px charcoal border, charcoal text;
     on dark: white border and text)
   - Container (max-width 1200px, 12-col grid, 24px gutters, 16px mobile side padding)
   - Section (96px vertical padding desktop, 64px mobile, takes a background prop)
   - Logo (renders an SVG from /assets by variant name)

5. Set up routes for: /, /managed-it, /phones, /cyber-security, /building-security,
   /services, /businesses, /nonprofits, /about, /contact, /privacy, /terms.
   Stub pages are fine. Do NOT create a security-assessment route — Pinnacle has
   its own assessment system and the site only links out to it.

HARD RULES — these override your defaults:
- Buttons are orange with CHARCOAL text. NEVER white text on orange. It fails contrast
  at 2.18:1 and is the single most common mistake on this project.
- Never use #F79862 for text or meaningful icons on white. Use #B84E14 instead.
- Border radius never exceeds 4px. No pill buttons, no large rounded cards, no
  glassmorphism. The logo is all sharp angles.
- Navy and bright blue are banned as primary colors. This brand exists to avoid the
  generic IT-provider look.
- No gradients on buttons, text, cards, or the logo.
- WCAG AA is non-negotiable. Use real <button>, <a href>, <input> + <label> elements.
  Never a clickable div. Visible focus states everywhere. Respect prefers-reduced-motion.

Confirm your understanding of the color and contrast rules before writing code.
```

---

## Prompt 2 — The shard motif

> Run this right after the scaffold. Do not let the model invent this one — it is the brand's visual signature and generic AI output gets it wrong.

```
Create a reusable <Shard /> component. This is the brand's signature graphic, taken
from the logo mark: a diagonal parallelogram band at 45 degrees, rising left to right,
fading out along its length.

Use exactly this geometry and gradient approach:

<svg viewBox="0 0 400 400" preserveAspectRatio="none" aria-hidden="true">
  <defs>
    <linearGradient id="shard-orange" x1="0" y1="1" x2="1" y2="0">
      <stop offset="0%"   stop-color="#F79862" stop-opacity="1"/>
      <stop offset="100%" stop-color="#F79862" stop-opacity="0"/>
    </linearGradient>
    <linearGradient id="shard-steel" x1="0" y1="1" x2="1" y2="0">
      <stop offset="0%"   stop-color="#737373" stop-opacity="0.55"/>
      <stop offset="100%" stop-color="#737373" stop-opacity="0"/>
    </linearGradient>
    <linearGradient id="shard-teal" x1="0" y1="1" x2="1" y2="0">
      <stop offset="0%"   stop-color="#0E4A55" stop-opacity="1"/>
      <stop offset="100%" stop-color="#0E4A55" stop-opacity="0"/>
    </linearGradient>
  </defs>
  <polygon points="0,400 240,160 340,160 100,400" fill="url(#shard-orange)"/>
</svg>

Props: variant ("orange" | "steel" | "teal"), plus standard positioning classes.

Rules:
- One to three shards per section, never more. Never a repeating pattern.
- Shards bleed off the edge of their container — they are always partially cropped.
- Gradients appear ONLY on shards. Nowhere else in this project.
- Always aria-hidden, always behind content (negative z-index or absolute + -z-10).
- Best placements: behind the hero photo, behind team headshots, as a corner accent
  on dark sections.

Render three example placements so I can check the angle and crop.
```

---

## Prompt 3 onward — one section at a time

> For each section: paste `00-master-prompt.md`, then the detail file(s) in the table, then the instruction line.

**The wrapper to use every time:**

```
[Paste 00-master-prompt.md]

[Paste the detail file(s) for this section]

Build ONLY the section named below. Do not build anything else. Do not modify
components outside this section. Use the copy from 01-content.md verbatim — do not
rewrite, shorten, or improve it.

PLACEHOLDER POLICY: anything in [square brackets] is content that does not exist yet.
Render it as a visibly styled placeholder block in warmLight with steel text showing
the bracketed label. NEVER invent a statistic, a testimonial, a client name, a client
logo, or a photo. NEVER substitute stock photography. A visible gap is correct here;
a fabricated detail is not.

Section to build: <SECTION NAME>
```

**The build queue:**

| # | Section | Paste | Instruction line |
|---|---------|-------|------------------|
| 1 | Header | 00 + 04 | Sticky header. Logo + tagline left, nav centre, phone and primary button right. 1px border appears once scrolled. Mobile: hamburger overlay, but phone number and CTA stay visible outside it. |
| 2 | Hero | 00 + 01 + 02 | Text left, photo right. H1 in Outfit 300 with "actually answers the phone" at weight 600. Orange shard behind the photo slot. Photo is a placeholder. |
| 3 | Proof strip | 00 + 01 | One row under the hero. Four stats, then a client logo row. Three of four stats are bracketed placeholders — render them as such. |
| 4 | Stakes | 00 + 01 | Text-led, no imagery. Heading, paragraph, three bulleted questions, closing line. Background warmLight. |
| 5 | Value proposition | 00 + 01 + 04 | Heading, intro, 4-column card grid (1 col mobile, 2 tablet). Each card: line icon, title, one sentence, "Learn more" link. Button below. |
| 6 | Who we serve | 00 + 01 + 04 | Two side-by-side cards, each with a photo placeholder, title, paragraph, button. |
| 7 | Guide | 00 + 01 + 02 | Photo placeholder one side, empathy + authority copy the other. Three testimonial cards below — all three are placeholders. |
| 8 | Plan | 00 + 01 | Three numbered steps, horizontal on desktop, stacked on mobile. Large numerals. Primary button below. |
| 9 | Lead generator | 00 + 01 + 02 | Full-width deepTeal band with an orange shard accent. Must read as a separate offer, not another section. Heading, copy, button, microcopy. |
| 10 | Success vs. failure | 00 + 01 + 04 | Two columns, five contrasting rows, closing line. **On mobile, pair each row as a labelled without/with unit — do NOT render two sequential lists.** |
| 11 | Explanatory paragraph | 00 + 01 | Single centred column, 60–75 character measure, visually quiet. This is the SEO block. |
| 12 | Final CTA | 00 + 01 + 02 | Full-width band, large headline, one primary button, secondary text link. No competing buttons. |
| 13 | Footer | 00 + 01 + 04 | deepTeal background, reversed logo, four columns, NAP, bottom bar. Service-area town list is a placeholder. |

---

## Correction prompts

**When it drifts from the brief:**

```
Stop. Re-read 00-master-prompt.md and 02-design-direction.md. The output you just
produced violates these ground rules:
- [list them specifically]
Rebuild this section from scratch following the brief exactly. Do not carry over the
previous version.
```

**When it invents content:**

```
You introduced content that does not exist in 01-content.md: [name it]. The brief
forbids inventing statistics, testimonials, client names, and logos. Replace it with
a visible placeholder block showing the bracketed label from 01-content.md.
```

**When buttons come out wrong:**

```
The primary button is using white text on orange. That combination fails WCAG AA at
2.18:1 and is explicitly banned in 02-design-direction.md. Primary buttons are orange
#F79862 background with charcoal #231F20 text, hover background #E8834A. Fix every
instance across the project.
```

**When it uses stock photos:**

```
Remove the stock photography. This brand requires real black-and-white cutout photos
of the Pinnacle team, which do not exist yet. Replace each one with a styled
placeholder block in warmLight showing the photo description from 01-content.md.
```

---

## Check before you call it done

Run through this after the homepage is assembled:

- [ ] **No white text on an orange button**, anywhere
- [ ] **No invented numbers** — the three bracketed stats still read as placeholders
- [ ] **No stock photos** — every photo slot is a labelled placeholder
- [ ] **No navy or bright blue** anywhere in the palette
- [ ] **No border radius above 4px**, no pill buttons
- [ ] **Gradients only on shards** — not on buttons, cards, or text
- [ ] The primary CTA uses **one label** across header, hero, plan, and final CTA
- [ ] Logos are `<img>` tags pointing at the SVGs in `/assets` — **"pinnacle" is never live text**
- [ ] Section backgrounds alternate: white → warmLight → white → deepTeal → white → tealMist → deepTeal footer
- [ ] Steel `#737373` appears only on captions, never on paragraphs
- [ ] The comparison table pairs its rows on mobile rather than splitting into two lists
- [ ] Tab through the page: visible focus on every interactive element
- [ ] **No writing instruction has leaked into visible copy.** Read the rendered page, not the brief. This one actually happened: a results page shipped the line *"…the specific actions that would close the gaps — calm, in priority order, no scare tactics."* The trailing phrase was a directive to the builder, not copy for a visitor. It breaks no brand rule, so no other check catches it. Scan for directive words in body text: *calm, plain-spoken, no scare tactics, boilerplate, concise, in priority order, respectful*
- [ ] Lighthouse mobile: LCP under 2.0s, accessibility 100

---

## Known limits of this approach

Two things in the brief are unlikely to survive an AI build without hand-correction, and that is expected:

**The photography.** The visual identity is built around B&W cutout people over shards. Until those photos exist, the hero and guide sections will look unfinished no matter how good the prompt is. That is a camera problem, not a prompt problem.

**The shard placements.** Prompt 2 gives exact geometry, but tasteful cropping and placement across a dozen sections is hand work. Expect to nudge them.
