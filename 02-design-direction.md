# 02 — Design Direction

> Use this file when building any UI component, page layout, or visual element.
> Paste this alongside 00-master-prompt.md when starting a design-heavy build.

**Source:** the Pinnacle Technology Solutions Brand Guide (9 Nov 2026). Color values and logo variants were pulled from the Pinnacle Figma file (*Pinnacle Technology Solutions Logo Styles*). Fonts, layout rules, and voice are recommendations built around that identity. Where a value below is marked **[suggested — confirm]** it is not from Figma.

---

## Aesthetic Direction

- **Vibe keywords:** steady, local, plain-spoken, sharp-angled, accountable
- **Overall tone:** confident without hype. The site should feel like meeting the owner and his team, not a faceless national provider.
- **Light or dark theme:** Light. Mostly white pages, punctuated by one or two Deep Teal or charcoal bands per page.
- **Density:** Airy and open — lots of white space, square-cornered geometry, one obvious next step on every screen.
- **The visual idea behind the logo:** an upward, ascending peak built from diagonal shards. It reads as climbing to the top, which is what Pinnacle does for clients: gets their technology to where it should be and keeps it there.

---

## Color Palette

**Ratio target:** roughly 60% white or light neutral, 20% charcoal or Deep Teal, 10% orange, 10% supporting accents. Orange carries energy and calls to action; Deep Teal carries trust and gives the page its weight. **Every page should show both.**

| Role | Token | Hex | Usage |
|------|-------|-----|-------|
| Background | White | `#FFFFFF` | Page background, text on dark |
| Alt background | Warm Light | `#F7F5F2` | Alternate section background **[suggested — confirm]** |
| Alt background (cool) | Teal Mist | `#E3F1EF` | Cool alternate section background, info callouts **[suggested — confirm]** |
| Primary | Pinnacle Orange | `#F79862` | Buttons, icons, shards, highlights, the mark |
| Primary (dark pair) | Deep Teal | `#0E4A55` | Hero and feature bands, footer, dark sections, headings on light tints |
| Text primary | Charcoal | `#231F20` | Body text, headings, dark sections |
| Text secondary | Steel Gray | `#737373` | Secondary text, captions, gradient ends — **captions only, not paragraphs** |
| Link / small orange text | Orange Text | `#B84E14` | Orange-colored links and small text on white |
| Accent (mid) | Teal | `#1F7A7A` | Secondary buttons, icons, links on white **[suggested — confirm]** |
| Accent (bright) | Sea Glass | `#5FC4BE` | Highlights and small accents **on Deep Teal or charcoal only** **[suggested — confirm]** |
| Accent (warm) | Amber | `#F5B841` | Badges, star ratings, small highlights on dark backgrounds **[suggested — confirm]** |
| Tint (warm) | Orange Tint | `#FEF0E8` | Callout boxes, highlighted cards **[suggested — confirm]** |
| Tint (warm alt) | Amber Cream | `#FDF3DC` | Warm callout background, testimonial cards **[suggested — confirm]** |
| Hover | Ember | `#E8834A` | Hover and pressed state for orange buttons **[suggested — confirm]** |
| Border | — | `#E5E5E5` | Dividers, card outlines |
| Input border | — | `#BDBDBD` | Form field borders |
| Success | — | `#1E7F5C` | Forms and alerts only, never decoration |
| Warning | — | `#8A5A00` | Forms and alerts only |
| Error | — | `#B3261E` | Forms and alerts only |
| Black | — | `#000000` | Logo wordmark only — prefer Deep Teal or Charcoal for dark backgrounds |

### Contrast rules — these override brand preference

WCAG AA needs 4.5:1 for body text, 3:1 for meaningful graphics.

| Combination | Contrast | Verdict |
|-------------|----------|---------|
| Orange `#F79862` text on white | 2.18:1 | **Fails.** Never use for text or meaningful icons on white |
| Charcoal on orange button | 7.47:1 | Passes — **the default button style** |
| Charcoal on Ember (hover) | 6.04:1 | Passes |
| Orange on black | 9.62:1 | Passes. Headings and accents on dark sections |
| Orange Text `#B84E14` on white | 5.08:1 | Passes. Links and small orange text |
| Steel Gray on white | 4.74:1 | Passes, barely. Captions only |
| Charcoal on white | 16.3:1 | Passes. Default body text |
| White text on Deep Teal | 9.86:1 | Passes — default text on teal bands |
| Orange on Deep Teal | 4.52:1 | Passes for headings and large text; avoid for small body text |
| Sea Glass on Deep Teal | 4.76:1 | Passes. Accent text and icons |
| Amber on charcoal | 9.17:1 | Passes |
| Amber on Deep Teal | 5.55:1 | Passes |
| Teal `#1F7A7A` text on white | 5.09:1 | Passes. Links and secondary buttons |
| Orange text on Teal `#1F7A7A` | 2.33:1 | **Fails.** Never pair these as text/background |

> **The single most common mistake to avoid: white text on an orange button.** Buttons are orange with charcoal text.

### How to combine them

- Orange and Deep Teal are the signature pairing. Example: a Deep Teal hero band with white headline text, one word in orange, and an orange button with charcoal text.
- **Alternate section backgrounds down the page:** White → Warm Light → White → Deep Teal band → White → Teal Mist → Charcoal or Deep Teal footer. This rhythm is what keeps the page from feeling flat.
- Use **one** supporting accent per section. Teal and amber in the same block start to look like a sports team.
- Never place orange and teal side by side as equal-weight fills — no half-and-half split backgrounds.
- The teal family is deliberately green-leaning, not navy, so the site avoids the generic blue MSP look.

---

## Typography

Both fonts are free on Google Fonts. **Load only these weights: Outfit 300, 400, 500, 600 and Inter 400, 600.**

| Role | Font | Weight | Desktop size / line height | Mobile size |
|------|------|--------|---------------------------|-------------|
| Hero headline (H1) | Outfit | 300 Light, key words 600 | 56px / 1.1 | 38px |
| Section heading (H2) | Outfit | 400 Regular | 40px / 1.15 | 30px |
| Card heading (H3) | Outfit | 500 Medium | 24px / 1.3 | 21px |
| Eyebrow label | Inter | 600, uppercase, 0.08em tracking | 13px / 1.4 | 12px |
| Body | Inter | 400 | 18px / 1.6 | 17px |
| Small / caption | Inter | 400 | 14px / 1.5 | 14px |
| Button | Inter | 600 | 16px / 1 | 16px |

**Rules:**
- Headings are **sentence case**. Never set headings in all caps.
- **The signature move:** pair light and bold weights inside one headline — e.g. "IT that **actually answers the phone**" with the emphasized words at 600, optionally in orange on dark backgrounds.
- Body line length stays between 60 and 75 characters.

> Outfit is a **[suggested — confirm]** stand-in: the Figma file has no live text or text styles, so the wordmark's original typeface is unknown. Outfit was chosen because its thin, round, geometric shapes echo the wordmark without copying it.

---

## Logo System

The logo is a three-shard peak mark plus a lowercase "pinnacle" wordmark with "technology solutions" beneath it. The dot of the "i" is a small orange triangle. **The wordmark is outlined artwork — it must always be placed as an image file.**

| File | Use it for |
|------|-----------|
| `pinnacle-logo-horizontal-color.svg` | Default. Site header and footer on white or light backgrounds |
| `pinnacle-logo-horizontal-reversed.svg` | Orange mark, white wordmark. Default on Deep Teal and charcoal |
| `pinnacle-logo-horizontal-white.svg` | All white. Over photos or busy backgrounds |
| `pinnacle-logo-horizontal-black.svg` | One-color use on light backgrounds |
| `pinnacle-logo-horizontal-orange.svg` | Sparing accent on black or charcoal only — never on white |
| `pinnacle-mark-orange.svg` | Favicon, loading states, section accents, social avatars on dark or Deep Teal |
| `pinnacle-mark-black.svg` / `pinnacle-mark-white.svg` | One-color mark on light or dark |
| `pinnacle-app-icon.svg` | Orange square with white mark: favicon at small sizes, app tile, social profile |

The orange mark on Deep Teal passes the 3:1 graphics threshold at 4.52:1. A stacked version exists in Figma — use it only where a square-ish space needs the full name, such as a social share image.

**Sizing and spacing:**
- Clear space equal to half the mark's height on every side.
- Minimum width: horizontal logo 140px on screen. Below that, use the mark alone.
- Minimum mark size: 24px tall. The favicon uses the app icon file, not the bare mark.
- Header: logo 36–44px tall on desktop, 28–32px on mobile.

**Never:**
- Stretch, skew, rotate, or recolor the logo outside the variants above.
- Put the color logo (black wordmark) on dark or busy backgrounds.
- Add drop shadows, outlines, glows, or gradients to the logo.
- Rebuild the wordmark in a font, or change "pinnacle" to title case.
- Separate "technology solutions" from "pinnacle" in the horizontal or stacked lockups.

---

## Graphic Language

**The shard motif** — the site's visual signature, taken from the logo mark:
- Diagonal parallelogram bands at about 45°, rising left to right, matching the angle of the logo mark.
- One to three shards per section, bleeding off the edge of the container. **Never fill a section with a pattern of them.**
- Best placements: behind the hero photo, behind team headshots, as a corner accent on dark sections.
- Three flavors: orange fade (default), steel fade, and a deep teal fade (`#0E4A55` → transparent) on light sections.

**Gradients** (from the Figma email signatures):

| Gradient | Stops | Use |
|----------|-------|-----|
| Orange fade | `#F79862` 100% → `#F79862` 0% | Main shard behind a person or headline |
| Steel fade | `#FFFFFF` → `#737373` | Secondary shard behind photos on light backgrounds |
| Orange to white | `#F79862` → `#FFFFFF` | Soft accent shard, low emphasis |

> **Gradients only ever appear on shards.** Never on buttons, text, cards, or the logo.

---

## Imagery & Media

- **Photography style:** real photos of Jeremy and the team are **required** on the home page and About page. No stock photos of people.
- **Treatment:** subject cut out from the background, converted to black and white, placed over orange and steel shards — like the Figma email-signature banners, which are the reference. On Deep Teal bands, use an orange shard behind the person plus a deep teal fade shard to tie the photo into the section.
- **Supporting photos:** client offices, on-site installs, network closets Pinnacle actually built — stay in color but slightly desaturated.
- **Icon set:** simple line icons, 1.5–2px stroke, charcoal on light or white on dark. Orange reserved for a single highlighted icon per group.
- **Video usage:** none at launch. No autoplay video with sound, ever.

---

## Reference Sites

**[Open item — no reference URLs were captured during the brand work.]** The Figma email-signature banners are the only visual reference on file, and they are the reference for the shard-plus-cutout-photo treatment. If reference URLs get collected later, add them here — a URL is worth 500 words of description.

**What to look at instead, in priority order:**
1. The Figma file *Pinnacle Technology Solutions Logo Styles* — logo variants and the three email-signature banners.
2. The Pinnacle Homepage Wireframe (desktop 1440 and mobile 390 artboards) — layout and section order are already resolved there.

---

## Layout & Spacing

- **Max content width:** 1200px, 12-column grid, 24px gutters. Mobile side padding 16px.
- **Spacing scale (px):** 4, 8, 12, 16, 24, 32, 48, 64, 96, 128.
- **Section padding:** 96px top and bottom on desktop, 64px on mobile.
- **Border radius: 0 to 4px.** The logo is all sharp angles — avoid pill shapes and large rounded cards.
- **Shadow style:** essentially none. Use 1px `#E5E5E5` borders instead of shadows.
- **Grid system:** 12-column.

---

## Components

| Component | Spec |
|-----------|------|
| Primary button | Orange `#F79862` fill, charcoal `#231F20` text, Inter 600 16px, 14px × 28px padding, 2px radius. Hover: background darkens to Ember `#E8834A` |
| Secondary button | Transparent, 2px charcoal border, charcoal text. On dark: white border and text |
| Text link | Orange Text `#B84E14`, underlined on hover |
| Header | White, logo left, 4–5 nav items, phone number visible, primary button right. Sticky, with a 1px `#E5E5E5` bottom border once scrolled |
| Cards | White on Warm Light `#F7F5F2` sections, 1px `#E5E5E5` border, 4px orange top border **for the featured card only** |
| Dark band | Charcoal or Deep Teal full-width section, white text, orange shard accent. Use once or twice per page |
| Footer | Deep Teal background, reversed logo (orange mark, white wordmark), address, phone, service-area towns, short nav |
| Forms | 48px tall inputs, 1px `#BDBDBD` border, 2px orange focus ring, labels always visible above fields |

---

## Animation & Motion

- **Animation level:** subtle only.
- **Preferred style:** fade and rise 16px on scroll, 200–300ms.
- **Hover states:** color shift only (orange → Ember; links gain an underline).
- **Banned:** parallax, 3D, autoplay video with sound, page-load animations.
- **Respect `prefers-reduced-motion`.**

---

## Performance

- Target under **2 seconds** load on mobile.
- SVG logos, compressed WebP photos, **two font families maximum**.

---

## What to Absolutely Avoid

> *Non-negotiables. These override any AI defaults.*

- **NO white text on orange buttons** — buttons are orange with charcoal text
- **NO navy or bright blue as a main color** — that is the generic MSP look this brand exists to avoid
- **NO retyping "pinnacle" as live text** — always place the logo SVG
- NO pill buttons, large rounded cards, or glassmorphism
- NO gradients on anything except shards
- NO stock photos of people, servers, or circuit boards
- NO glowing circuit boards, binary code, padlock-on-blue icons, hooded hackers, or handshake stock photos
- NO server rooms that are not Pinnacle's
- NO section filled with a repeating shard pattern — one to three per section, bleeding off the edge
- NO invented statistics, testimonials, or client logos — leave clearly labeled placeholders
- NO generic "nationwide" language — this is Fort Wayne and northeast Indiana
- NO Lorem Ipsum or placeholder text in place of the real copy in 01-content.md
- NO fonts other than Outfit and Inter

> **Template override:** the generic version of this file bans Inter. That does not apply here — **Inter is the specified body font for this brand.** Outfit for headings, Inter for body.
