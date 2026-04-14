# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.
LA información de la empresa esta en [brief-landing.md](brief-landing.md)
## Project

Single-page static marketing landing for **coherenceLab** (coerence.tech), in Spanish. The entire site lives in `index.html` — there is no build system, package manager, or backend.

## Architecture

- **Single file**: `index.html` contains markup, inline Tailwind config, inline `<style>` block, and inline `<script>` for scroll reveal / nav behavior.
- **Tailwind via CDN**: `https://cdn.tailwindcss.com` with a custom theme defined inline (`tailwind.config = {...}`). Brand tokens: `ink` / `ink2` (dark bg), `ivory` / `paper` (light bg), `accent` (#10B981 emerald), `line`, `muted`. Fonts: `Inter` (sans) and `Fraunces` (display) loaded from Google Fonts.
- **Custom CSS utilities** in the inline `<style>`: `.bg-grid`, `.bg-grid-light`, `.radial-fade`, `.reveal` (scroll-triggered via IntersectionObserver), `.grad-text`, `.ring-dotted`, `.noise`, `.nav-link`.
- **No framework, no bundler, no tests.** Editing = edit `index.html` directly.

## Running locally

Open `index.html` in a browser, or serve the directory statically (e.g. `python3 -m http.server`). No install step.

## Conventions

- Copy is Spanish (`<html lang="es">`) — preserve language and tone when editing content.
- When adding styles, prefer Tailwind utility classes with the existing theme tokens; only add to the inline `<style>` block for effects Tailwind can't express.
- Keep everything in `index.html` unless the user explicitly asks to split into separate assets.