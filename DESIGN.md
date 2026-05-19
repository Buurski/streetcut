# Design notes — Street Cut Landing

Loose guide. Use as scaffold for similar editorial landing pages.

## Tone

Editorial, restrained, Scandinavian. Not corporate, not loud. Reads like a small print magazine spread — confident with whitespace, sparing with color. Danish copy is short, fragmentary, lowercase except where grammar demands it.

## Type system

Two-family pair, no third.

- **Serif (display + accents):** EB Garamond, weights 400/500 + italic 400. Used for H1, H2, H3, price names, salon headings, quote, footer claim. Italic does emotional lifting — pairs a sober roman lead-line with an italic kicker ("Faste priser. *Ingen overraskelser.*").
- **Grotesk (UI + body):** Inter Tight, weights 400/500. Body copy, eyebrows, nav, buttons, captions.

Sizing is fluid via `clamp()`. Hero H1 scales 64–144px. Section H2 scales 38–56px. Body is fixed 17px.

Tracking is tight on serif display (`-0.024em` on H1, `-0.018em` on H2) and slightly open on grotesk eyebrows (`0.18em` letter-spacing, uppercase, 11px).

## Color

Five tokens. No gradients. No shadows except focus/hover lifts.

```
--bone:        #EFE8DA   /* base background */
--bone-deep:   #E5DCC7   /* hover, alt-mode bg */
--ink:         #142235   /* primary text + CTAs */
--ink-deep:    #0B1726   /* CTA hover */
--ink-soft:    #3E5878   /* secondary text + hairlines */
--accent:      #A37A4F   /* single warm accent, used 1× per section max */
```

Hairlines use `--ink-soft-30` (rgba 0.32) at 0.5px — that thinness is the look. Don't replace with 1px solid.

## Layout

- `--maxw: 1320px`, `--gutter: clamp(20px, 4vw, 56px)`, `--sect: clamp(80px, 11vw, 160px)` for vertical section padding.
- `.wrap` is the only container — no nesting, no helper wrappers.
- Sections share `.sect-head` two-column pattern: numbered eyebrow + serif H2 on the left, grotesk blurb on the right, aligned to baseline.
- Numbered eyebrows ("01 — Priser") with a 18px hairline before the text. One per section, monotonically.

## Motion

Single easing curve: `cubic-bezier(0.22, 1, 0.36, 1)`. Used for all transitions. Don't introduce a second curve.

Animation palette:
- **Reveal-line** — H1 lines split into `.reveal-line > .inner`, translateY(115%) → 0, staggered 80ms apart, 700ms duration.
- **Image wipe** — hero `::after` overlay scaleX(1) → scaleX(0), 1100ms, delay 320ms.
- **Fade-up** — opacity + 20px translateY, triggered by IntersectionObserver at 18% threshold with -10% bottom rootMargin.
- **Parallax** — hero portrait Y-shift ±8px tied to scroll position. Subtle.
- **Magnetic CTA** — primary buttons pull toward cursor when inside 110px radius. Max travel 6px × force-curve, computed via `dx/RADIUS * STRENGTH * force * 4`.
- **Wipe-underline** — `.link-wipe::after` scaleX(0) → scaleX(1) on hover. `is-static` variant inverts (starts visible, wipes out from the right).
- **Sticky nav** — opacity-mounted bone bg + 14px backdrop blur after 24px scroll. Padding shrinks 22→14px.

`prefers-reduced-motion: reduce` short-circuits to 0.001ms transition-duration and forces all reveal classes on at load.

## Interaction patterns

- CTAs are dark filled rectangles, 1px corner radius (not 0, not 4). The square-but-not-quite radius is the detail.
- Buttons have a 6px bone dot to the right of label — quiet rhythm marker, also visually balances the centered text.
- Salon thumbnails scale 1.02 → 1.06 on hover, filter desaturate slightly. 900ms duration — slow on purpose.
- Service tiles flip background to `--bone-deep` on hover + arrow translates 6px right.
- Price rows shift left padding 0 → 12px on hover with bone-deep bg.

## Editorial detail

- "№" glyph for numbering, not "#" or "No.".
- Currency formatted as `<span class="price-num">399<span class="kr">kr</span></span>` — main number in grotesk medium, "kr" in ink-soft, regular weight, 4px gap. Tabular-nums variant.
- "·" middle dot in eyebrows ("København · Odense"). Not bullets, not hyphens.
- Italic kicker after a roman lead is the rhetorical move — sets up, then leans in.

## What to copy when building another site

1. Two-font pair (1 serif italic-capable + 1 grotesk). No third.
2. 5-token color palette with one warm accent reserved for ≤1 dot per section.
3. Numbered section heads with hairline rule.
4. Single easing curve for every transition.
5. Type entrance: reveal-line for hero, fade-up for everything else.
6. Magnetic CTAs only on primary buttons. Don't apply to secondary links.
7. Hairlines at 0.5px solid `--ink-soft-30`. Resist 1px.
8. Asset paths: `assets/photos/<group>/<slug>.png` with lazy loading on below-fold images.
