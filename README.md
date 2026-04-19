# Altera Landing Page (Astro)

Component-based Astro version of the Altera v3 landing page. Designed for AI-assisted editing in [bolt.new](https://bolt.new) — each section lives in its own file so you can edit any part without touching the rest.

## Project structure

```
src/
├── pages/
│   └── index.astro              ← page composition (imports + orders sections)
├── layouts/
│   └── BaseLayout.astro         ← <html>, <head>, fonts, body, nav-scroll script
├── styles/
│   └── global.css               ← design tokens, reset, typography utilities
├── lib/
│   └── logo.ts                  ← base64-encoded Altera logo (shared by Nav + Footer)
└── components/
    ├── Nav.astro                ← top navigation
    ├── Hero.astro               ← dark hero with "we don't hire reps" headline
    ├── Ticker.astro             ← scrolling territory marquee
    ├── Wedge.astro              ← 01 / The Wedge (grind vs system comparison)
    ├── Stack.astro              ← 02 / The Stack (six-layer infrastructure viz)
    ├── Path.astro               ← 03 / The Path (4-rung career ladder)
    ├── Map.astro                ← 04 / The Map (territory grid)
    ├── Culture.astro            ← 05 / Who Joins (checklist)
    ├── Operators.astro          ← 06 / The Operators (founder manifesto)
    ├── Voices.astro             ← 07 / The Voices (operator testimonials)
    ├── OffTheClock.astro        ← 08 / Off the Clock (photo mosaic)
    ├── Faq.astro                ← 09 / The Questions
    ├── FinalCta.astro           ← closing CTA
    ├── Footer.astro             ← site footer
    └── Lightbox.astro           ← shared <dialog> for Off the Clock photos
```

## Getting started

```bash
npm install
npm run dev
```

Open http://localhost:4321.

## Importing into bolt.new

1. Zip the entire `altera-astro/` folder.
2. Open https://bolt.new and create a new Astro project.
3. Drag-drop the zip or upload files.
4. Run `npm install` then `npm run dev` in the bolt terminal.

To edit a single section in bolt, just say "edit `Operators.astro`" or "change the headline in `Stack.astro`". The component scoping keeps changes surgical.

## Editing notes

- **Design tokens** (colors, type) → `src/styles/global.css` (`:root` block)
- **Section content** → individual component files
- **Section order** → `src/pages/index.astro`
- **Page-wide JS** (nav scroll) → `BaseLayout.astro`
- **Section-specific JS** (FAQ accordion, lightbox) → respective component files

## Design system

Same as v3:
- **Display:** Archivo Black (uppercase, condensed display)
- **Body:** Inter
- **Accents/Mono:** JetBrains Mono
- **Palette:** dark `#1A1D24` ink, `#38B6FF` blue, accents in lime + orange
