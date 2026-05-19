# CLAUDE.md — Street Cut

Guide for future Claude sessions on this repo and similar editorial landing-page projects.

## What this repo is

A single-page editorial landing site for Street-Cut — a Danish hair salon chain with five locations (Copenhagen + Odense). Produced from a Claude Design handoff bundle. Deployed as static HTML on Vercel.

- **Tech:** vanilla HTML + CSS + JS in a single file. No framework. No build step.
- **Fonts:** EB Garamond + Inter Tight via Google Fonts.
- **Assets:** `assets/photos/{hero,salons,atmosphere,products}/` + `assets/logos/`.
- **Hosting:** Vercel, static deploy.
- **Source of truth for design:** `DESIGN.md` + the prototype in `Street Cut-handoff/`.

## File map

```
Street Cut Landing.html        # production page
DESIGN.md                      # design system notes (read first when restyling)
CLAUDE.md                      # this file
assets/                        # photos + logos used by the page
Street Cut-handoff/            # original Claude Design export — design source of truth
strategy/                      # brief + references from client discovery
```

The handoff bundle stays in the repo as design provenance. Don't delete it.

## Working principles

1. **Read DESIGN.md before changing visual code.** The design system is intentional — every easing curve, hairline width, and font choice has a reason. Don't introduce a second easing, a third font, or 1px borders without checking.
2. **Keep the file singular.** No build step, no bundling, no extracted CSS file unless the page grows past ~1500 lines. The whole point of the prototype-as-production pattern is that the design lives in one readable artefact.
3. **The handoff prototype has a tweaks panel.** When you reference it, ignore React/Babel/`tweaks-panel.jsx` — that's design-tool infrastructure. The production page strips it and bakes the default tweak values in.
4. **Asset paths are root-relative** (`assets/photos/...`). The page sits at the repo root.
5. **Danish copy.** Don't autotranslate. Keep "Book tid", "Klip", "Saloner" as-is. Use proper Danish characters (æ, ø, å).

## CSS specificity gotcha

`.nav-links a` (specificity 0,1,1) overrides `.nav-cta` (0,1,0). The CTA button color must be set via `.nav-links a.nav-cta` (0,2,0), or it inherits the link color. The original prototype dodged this with an inline `style="color: rgb(239, 232, 218)"`; the production page fixes it at the selector level.

## Deployment

Vercel. Static deploy, no framework preset needed. `vercel --prod` from the repo root or merge to `main` for the GitHub→Vercel auto-deploy.

## When asked to add a section

Match the existing rhythm:
- Numbered eyebrow ("04 — Section name") with the hairline-before pattern via `.sect-num::before`.
- Serif H2 with optional `<span class="accent-dot">` and an italic kicker on the second line.
- Right-column blurb at `max-width: 38ch`, color `--ink-soft`, font-size 16px.
- Wrap content in `.section` for vertical padding, `.wrap` for horizontal gutter.

## When asked to redo this for another business

Look at `DESIGN.md` last section ("What to copy when building another site"). The system transfers — swap content, photos, color tokens, and the brand name in the SVG logo defs. Keep the type pair, easing curve, motion palette, and `.sect-head` rhythm.

## What not to do

- Don't add Tailwind, React, or any framework. The page works because it's small and direct.
- Don't replace `var(--ease)` with a different curve. One curve for the whole site.
- Don't widen hairlines past 0.5px.
- Don't add a second accent color. `--accent` (#A37A4F) is the only warm.
- Don't add emojis to copy. The brand voice doesn't carry them.
- Don't generate placeholder images — only use the real photos in `assets/`.
