# AGENTS.md

## Architecture

This is a single static HTML file (`index.html`) with inline `<style>` and `<script>` — no build step, no framework, no dependencies. Netlify publishes the repo root as-is (see `netlify.toml`).

## Key directories

- `index.html` — all markup, styles, and behavior (photo modal, GitHub link routing) live here.
- `img/` — static images referenced from `index.html`. Reference them through the Netlify Image CDN (`/.netlify/images?url=/img/<file>&w=<width>&fm=webp`) rather than the raw file.

## Conventions

- Color palette is intentionally minimal: near-black (`#1a1a1a`) and white, with a single blue accent (`#2563eb`) used for highlighted text/links. Avoid introducing new colors.
- The "Featured Projects" section uses `.project-card` as a flex row; a card with a `.project-image-side` child spans the full grid width (`grid-column: 1 / -1`) and stacks to a column on mobile. Keep the image as the first child so it renders on the left on desktop.
- No CSS framework — hand-written, scoped selectors in the `<head>`.
