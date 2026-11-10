# 04 — Site Structure & Layout

> Use this file when building navigation, page layouts, or any structural scaffolding.
> Paste this alongside 00-master-prompt.md when starting a new page or layout session.

**Source:** the Pinnacle Homepage Wireframe (Claude Design — desktop 1440px and mobile 390px artboards) and the Pinnacle Homepage Copy doc. The homepage section order below is already resolved in the wireframe — **use it as the build sequence.** Copy for every section lives in 01-content.md.

---

## Site Map

| Page | Route | Priority | Notes |
|------|-------|----------|-------|
| Home | `/` | P1 | The whole StoryBrand sequence in one page. 12 sections — see below. |
| Managed IT | `/managed-it` | P1 | Network and devices. Linked from value-prop card 1. |
| Phones | `/phones` | P1 | Linked from value-prop card 2. |
| Cyber Security | `/cyber-security` | P1 | Linked from value-prop card 3. |
| Building Security | `/building-security` | P1 | Cameras and door access. Linked from value-prop card 4. |
| Services index | `/services` | P1 | Target of the "See All Services" button. Can be a simple hub of the four above. |
| IT for Businesses | `/businesses` | P1 | Audience page. Target of "IT for Businesses". |
| IT for Nonprofits and Ministries | `/nonprofits` | P1 | Audience page. Carries the nonprofit-discount and donor-data angle. |
| About | `/about` | P1 | Jeremy and the team, with real B&W cutout photos. Trust page — referrals land here. |
| Free Security Assessment | `/security-assessment` | P1 | The transitional CTA. Nav item on every page. |
| Assessment results | `/security-assessment/results` | P1 | Score + action list, with the primary CTA directly under the list. **[depends on the assessment tool]** |
| Contact | `/contact` | P1 | Form plus NAP and hours. |
| Privacy Policy | `/privacy` | P1 | Legal — can be simple, but the assessment collects emails so it must be real. |
| Terms | `/terms` | P1 | Legal — can be simple. |
| Service-area pages | `/it-support/[town]` | P2 | Strong local-SEO play for this category. Needs the town list. |
| Blog index | `/blog` | P3 | Only if there is a real plan to publish. |

**P1 is 14 pages**, but ten of them are short. The homepage carries the argument; the service and audience pages exist mostly so the homepage cards have somewhere to go and so local search has pages to rank.

---

## Navigation

**Header nav:**
- **Style:** Sticky top bar. White background, 1px `#E5E5E5` bottom border appears once scrolled.
- **Logo position:** Left, 36–44px tall on desktop, 28–32px on mobile. Logo tagline "All your tech. One call." sits with it in the header.
- **Nav links:** Services · Who We Serve · About · Free Security Assessment · Contact
- **Phone number:** `Call (260) 205-8900` always visible in the header.
- **CTA in nav:** Yes — **Book an IT Walkthrough** (primary button, right side)
- **Mobile nav:** Hamburger opening a full-screen overlay. The phone number and the primary CTA stay visible outside the hamburger — they are the two things a mobile visitor is most likely to want.
- **Transparent on hero?** No — always solid white.

> **Free Security Assessment stays in the nav on every page.** It is the lowest-commitment way in and should never be more than one click away.

**Dropdowns:** Services and Who We Serve each have 4 and 2 children respectively. Keep them as simple dropdowns on desktop and expanded groups in the mobile overlay. No mega-menu.

---

## Homepage Section Order

> Twelve sections, in conversion order. Section backgrounds alternate per the rhythm in 02-design-direction.md: White → Warm Light → White → Deep Teal band → White → Teal Mist → Deep Teal footer. Do not let two adjacent sections share a background.

1. **Header (sticky nav)**
   - Layout: logo + tagline left, nav centre, phone number and primary button right. Sticky.
   - Goal: make the phone number and the primary CTA reachable from anywhere on the page.

2. **Hero**
   - Layout: text left, photo right. H1 in Outfit 300 with "actually answers the phone" at 600. Subhead below, then primary button with the phone number beside it. Orange shard behind the B&W cutout photo of Jeremy on site.
   - Goal: name the pain and the fix in one line, and drive to the walkthrough.

3. **Proof strip**
   - Layout: a single row directly under the hero. Four short stats, then a row of client logos.
   - Goal: fast validation for referral traffic, which is how most visitors arrive.

4. **Stakes**
   - Layout: heading, short paragraph, then the three questions as a bulleted list. Text-led, no imagery.
   - Goal: agitate the problem and make the reader feel seen. No solution yet.

5. **Value proposition**
   - Layout: heading and intro, then a 4-column card grid. Each card: icon, title, one sentence, "Learn more" link. "See All Services" button below the grid.
   - Goal: show that one team owns everything, and route to the four service pages.

6. **Who we serve**
   - Layout: two side-by-side cards, each with a photo, title, paragraph, and button.
   - Goal: let both audiences self-identify immediately.

7. **Guide**
   - Layout: photo of Jeremy one side, empathy and authority copy the other. Three testimonial cards below, side by side on desktop.
   - Goal: the StoryBrand guide beat — empathy first, then credentials, then proof.

8. **Plan**
   - Layout: three numbered steps, horizontal on desktop. Large numerals. Primary button below.
   - Goal: remove the fear of "what happens if I call?"

9. **Lead generator**
   - Layout: **full-width Deep Teal or charcoal band** with an orange shard accent, so it reads as a separate offer rather than another section. Heading, copy, button, microcopy. Optional score-gauge graphic.
   - Goal: capture the visitors who are not ready to talk to a human.

10. **Success vs. failure**
    - Layout: two columns side by side — "Without one team watching" and "With Pinnacle" — five contrasting rows. Closing line centred below.
    - Goal: the SB7 stakes beat. Make the cost of doing nothing concrete without catastrophising.

11. **Explanatory paragraph (SEO)**
    - Layout: a single centred column of plain prose, 60–75 characters per line. Visually quiet.
    - Goal: the literal service list for search engines and for skimmers who want to confirm what Pinnacle actually does.

12. **Final CTA**
    - Layout: full-width band, large headline, one primary button, secondary text link below. No distractions.
    - Goal: one last conversion push, with the assessment as the fallback.

13. **Footer**
    - Layout: see Footer section below.
    - Goal: NAP, navigation, and local-SEO signals.

---

## Footer

**Structure:** Deep Teal background, reversed logo (orange mark, white wordmark). Four columns on desktop.

- **Brand column:** reversed logo, tagline "All your tech. One call.", address, phone, email, hours
- **Column 1 — Services:** Managed IT · Phones · Cyber Security · Building Security
- **Column 2 — Who We Serve:** Businesses · Nonprofits and Ministries
- **Column 3 — Company:** About · Free Security Assessment · Contact
- **Bottom bar:** © [year] Pinnacle Technology Solutions · Privacy Policy · Terms · Google review badge **[once reviews are collected]**
- **Social icons:** **[none confirmed — omit until there are real profiles to link]**
- **Newsletter in footer:** No

**Content:**
- 3249 N. Anthony Blvd., Fort Wayne, IN 46805
- (260) 205-8900
- info@pinnacletechnology.solutions
- Live phone and email support, Monday to Friday, 8:00 to 5:00
- Service-area town list **[pending — important for local SEO]**

---

## Component Needs

**Page-specific:**
- [ ] Service card with icon, title, one-line copy, and "Learn more" link (×4, one featured variant with a 4px orange top border)
- [ ] Audience card with photo, title, paragraph, button (×2)
- [ ] Stat block for the proof strip (×4)
- [ ] Client logo row — graceful when empty
- [ ] Testimonial card (×3), with a visible placeholder state until real quotes arrive
- [ ] Numbered plan step (×3)
- [ ] Two-column comparison table that becomes readable stacked pairs on mobile
- [ ] Full-width dark band with shard accent (used by sections 9 and 12)
- [ ] Shard graphic as a reusable positioned SVG — orange fade, steel fade, teal fade
- [ ] Sticky header with scrolled state
- [ ] Mobile nav overlay
- [ ] FAQ accordion
- [ ] Form field with always-visible label, 48px height, orange focus ring
- [ ] 404 page

---

## Responsive Behavior

Wireframe artboards: **desktop 1440px** and **mobile 390px**. Tablet behaviour is interpolated — follow the table.

| Section | Mobile (< 768px) | Tablet (768–1024px) | Desktop (> 1024px) |
|---------|------------------|---------------------|---------------------|
| Header | Logo + phone + CTA visible, nav in hamburger overlay | Logo left, condensed nav, CTA right | Full nav, phone, CTA |
| Hero | Stacked — photo below text, full width | Text left, photo right | Text left, photo right, wider |
| Proof strip | 2×2 stat grid, logos scroll horizontally | 4 across, logos wrap | 4 across in one row |
| Stakes | Single column | Single column, narrower measure | Single column, centred, max 1200px |
| Value proposition | 1 column | 2 columns | 4 columns |
| Who we serve | Stacked cards | 2 columns | 2 columns |
| Guide | Photo above copy; testimonials stack | Photo + copy side by side; testimonials 2-up | Side by side; testimonials 3-up |
| Plan | Stacked steps, numeral above each title | 3 columns, tighter | 3 columns |
| Lead generator | Full-width band, centred, button full width | Centred | Centred, max 1200px |
| Success vs. failure | **Stacked pairs** — each "without/with" row becomes a labelled pair, not two long lists | 2 columns | 2 columns |
| Explanatory paragraph | Single column, 16px side padding | Single column | Single column, 60–75ch measure |
| Final CTA | Stacked, button full width | Centred | Centred |
| Footer | Stacked, columns collapsed in order | 2 columns | 4 columns |

> The comparison table in section 10 is the one piece that genuinely breaks on mobile if handled naively. Do not let it become two sequential lists — pair each row.

---

## Interaction Patterns

- **Scroll behavior:** smooth scroll for in-page anchors only
- **Sticky elements:** header only
- **Scroll reveal:** fade and rise 16px, 200–300ms, once per element. Respect `prefers-reduced-motion`
- **Modal triggers:** none. The booking flow is a page or an embed, not a modal **[pending the booking decision in 03-tech-specs.md]**
- **Infinite scroll or pagination:** not applicable
- **Carousel/slider behavior:** testimonials are side by side on desktop and swipeable on mobile. No auto-play
- **Accordion behavior:** FAQ — one open at a time
- **Back to top button:** no
- **Pop-ups:** none. The brand guide bans competing buttons and pop-ups; one clear CTA per section

---

## Whitespace & Density

- **Section vertical padding:** 96px desktop, 64px mobile
- **Card internal padding:** 24–32px
- **Line height (body):** 1.6
- **Overall feel:** open and airy, with sharp 0–4px corners. Roomy and fast, one obvious next step on every screen.
