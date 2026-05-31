# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Presentation slides for a talk on cryptographic hash functions ("Dessine-moi un mot de passe"), built with Astro + Reveal.js. Content is in French. Deployed to GitHub Pages via CI on every push.

## Commands

- `pnpm dev` — start dev server
- `pnpm build` — production build
- `pnpm preview` — preview production build
- Package manager: **pnpm** (v9)

## Architecture

- **Astro 4.6** as the static site builder, **Reveal.js 5.1** for slide navigation
- Single page app: `src/pages/index.astro` assembles all slides in presentation order
- **Slide components** live in `src/slides/` organized by talk section:
  - `1_intro/`, `2_demo/`, `3_evaluate_a_hash_function/`, `4_cracking_hash_function/`, `5_outro/`
- **Reusable components** in `src/components/`:
  - `Slide.astro` — wrapper with auto-animate support, optional title/subtitle backgrounds (black + yellow gradient), and background images
  - `TitleSlide.astro` — title card variant
  - `CodeBlock.astro` — code display
- Reveal.js is initialized in `src/layouts/Layout.astro` with custom keyboard mapping (up=next, down=prev) and no transition animations
- Styles use Sass; brand color is `#ffeb03` (yellow)
- Base path is `/slides-fonction-hash` (configured in `astro.config.mjs`)
- No tests or linter configured
