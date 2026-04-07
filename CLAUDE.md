# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Personal portfolio website for Mark Anthony Morales — a Full-Stack Developer. Built with Vue.js 3 + Vite, deployed to GitHub Pages. Uses a Bento Grid layout with a Warm Navy + Gold color palette.

## Commands

- `npm run dev` — start local dev server
- `npm run build` — production build to `dist/`
- `npm run preview` — preview production build locally

## Architecture

Single-page Vue.js 3 app (Composition API, no Vue Router). The page is a responsive bento grid of card components.

- **`src/data/profile.js`** — single source of truth for all content (CV data). Edit this file to update site content.
- **`src/components/`** — 12 card components + ThemeToggle, each self-contained with scoped styles.
- **`src/assets/styles/`** — CSS architecture: `variables.css` (color tokens, dark mode), `grid.css` (bento layout), `cards.css` (shared card styles).
- **Custom CSS only** — no Tailwind, no Bootstrap. Color tokens as CSS custom properties with dark mode via `[data-theme="dark"]`.

## Deployment

GitHub Actions auto-deploys on push to `main`. Workflow at `.github/workflows/deploy.yml` builds and deploys to GitHub Pages. Base path is `/portfolio/`.

## Design Spec

Full design spec at `docs/superpowers/specs/2026-04-07-portfolio-website-design.md`.
