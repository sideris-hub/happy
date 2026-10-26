# for you 🌸

A one-page animated birthday greeting: an SVG flower garden grows and blooms, then a short poem fades in on top of it.

**Status:** working prototype (exported from Figma Make). No tests, no CI, no deploy config.

## Stack

- React 18 + TypeScript, Vite 6
- Tailwind CSS v4 (via `@tailwindcss/vite`), `tw-animate-css`
- Flower animation: jQuery 3.2.1, GSAP 3 and DrawSVGPlugin, loaded from CDNs at runtime
- Fonts: Google Fonts `Great Vibes` and `Special Elite`
- Package manager: pnpm

## Run locally

Requires Node.js and pnpm (`npm install -g pnpm`). No environment variables or `.env` are needed.

```sh
git clone https://github.com/sideris-hub/happy.git
cd happy
pnpm install
pnpm dev      # dev server
pnpm build    # production build into dist/
```

The page needs internet access: GSAP, jQuery, DrawSVGPlugin and the fonts come from external CDNs.

## Tests

There are no tests yet.

## Structure

```
index.html                 HTML entry
src/main.tsx               React entry
src/app/App.tsx            the whole page: poem text, timings, inline flower SVG
src/styles/                fonts, Tailwind and theme CSS
public/flowers/            flower animation script (GSAP timeline) and its CSS
vite.config.ts             Vite config
```

To edit the poem, change the `stanzas` array at the top of `src/app/App.tsx`. The `isTitle`, `isSpecial` and `isClosing` flags switch a stanza's styling.

## Why it's built this way

- **The SVG is inlined into the page** (`FLOWER_SVG_INNER` in `App.tsx`, rendered via `dangerouslySetInnerHTML`). The animation script in `public/flowers/flower-script.js` finds parts of the drawing by their IDs (`#Stem1_1_`, `#Leaf2_1_`…), which only works if the SVG is part of the DOM, not an `<img>` or an external file.
- **The SVG and animation are taken from the `flowers_garden` project** (HTML/CSS/JS) as-is, so the script is plain JS with jQuery and globals rather than React code. It is loaded with `<script>` tags at runtime, in order: jQuery → GSAP → DrawSVGPlugin → `flower-script.js`.
- **The poem appears after a fixed delay** of 14.5 s (`ANIM_DONE_MS`), chosen to cover the GSAP timeline plus a small buffer. If the animation changes, this number has to be updated by hand.
- **`postcss.config.mjs` is intentionally empty**: Tailwind v4 is wired in through the Vite plugin, which sets up PostCSS by itself.
- **All fonts are loaded with a single Google Fonts request**, and `index.html` preconnects to the Google Fonts hosts to reduce loading latency.
