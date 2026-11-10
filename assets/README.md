# Pinnacle Logo Assets

Exported from the Figma file **Pinnacle Technology Solutions Logo Styles**
(`XvNJcteTULKeLc51toIpg5`), page `Desktop - 1`, on 10 Nov 2026.

Usage rules for every file here live in `02-design-direction.md` → **Logo System**.
The short version: **place these as image files. Never retype "pinnacle" as live text.**

---

## Files

| File | Figma node | Artwork colors | Use it for |
|------|-----------|----------------|-----------|
| `pinnacle-logo-horizontal-color.svg` | `4:784` | Orange mark `#F79862` + black wordmark | **Default.** Header and footer on white or light backgrounds |
| `pinnacle-logo-horizontal-reversed.svg` | derived — see note | Orange mark `#F79862` + white wordmark | Default on Deep Teal and charcoal bands |
| `pinnacle-logo-horizontal-white.svg` | `37:53` | All white | Over photos or busy backgrounds |
| `pinnacle-logo-horizontal-black.svg` | `4:786` | Black + orange `i` dot — see note | One-color use on light backgrounds |
| `pinnacle-logo-horizontal-orange.svg` | `4:1005` | All orange `#F79862` | Sparing accent on black or charcoal **only** — never on white |
| `pinnacle-mark-orange.svg` | `4:810` | Orange `#F79862` | Favicon, loading states, section accents, avatars on dark or Deep Teal |
| `pinnacle-mark-black.svg` | `4:821` | Black | One-color mark on light backgrounds |
| `pinnacle-mark-white.svg` | `4:988` | White | One-color mark on dark backgrounds |
| `pinnacle-app-icon.svg` | `4:1001` | Orange square + white mark | Favicon at small sizes, app tile, social profile image |
| `pinnacle-logo-stacked-color.svg` | `4:772` | Orange mark + charcoal `#231F20` wordmark | Square-ish spaces needing the full name, e.g. social share images |
| `pinnacle-logo-stacked-white.svg` | `4:976` | All white | Stacked lockup on dark backgrounds |

---

## Three things worth knowing

**1. Backgrounds were stripped.** Figma's export wraps each node in two opaque
rects — a `#F5F5F5` backing rect and the full 1440×1024 artboard as a white
rect. Both were removed from every file, so these are transparent. Without that
step `pinnacle-logo-horizontal-white.svg` would have been white-on-white, and
none of them would sit on a Deep Teal band.

**2. The reversed variant was derived, not exported.** No orange-mark/white-wordmark
lockup exists in the Figma file. The brand guide describes it as "same shapes,
wordmark recolored white," so it was produced by taking
`pinnacle-logo-horizontal-color.svg` and changing the 9 wordmark paths from
`fill="black"` to `fill="white"`. The mark and all path geometry are untouched.
**Worth a human eyeball before it ships.**

**3. The "black" lockup is not strictly one-color.** `pinnacle-logo-horizontal-black.svg`
keeps the orange triangle on the `i` (10 black paths, 1 orange). That matches the
brand guide's description of the dot, but if you need a true single-ink version
for print or a partner logo grid, that path needs recoloring too.

Also note the horizontal lockups use pure `black` for the wordmark while the
stacked lockup uses Charcoal `#231F20`. Both come from the source file.

---

## Still missing from this folder

- Hero photo — Jeremy on site with a client
- Jeremy Nelson founder portrait
- Team headshot cutouts, names and titles
- "Who we serve" photos — office team, church/nonprofit staff
- Client logos for the proof strip, pending permission

See `hero-photo.jpg.txt` for the photo prep and compression workflow.
