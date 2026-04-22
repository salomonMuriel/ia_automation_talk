# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A single-file HTML slide deck for a live workshop ("Automatización + IA — Taller Ignia"). The deck was handed off from Claude Design (see `sesi-n-automatizaci-n-ia/` bundle if still present under `/tmp`). The authored artifact is `Automatizacion IA - Taller.html` — everything else is an asset it pulls in.

## Preview / dev loop

```bash
python3 -m http.server 8765
# open http://localhost:8765/Automatizacion%20IA%20-%20Taller.html
```

No build step. Edit the HTML, reload the browser. That's the whole loop.

## Architecture

The deck runs on a **custom web component**, `<deck-stage>`, defined in `deck-stage.js` (~620 lines, vanilla JS, no framework). Reading the header comment of that file is the fastest way to understand the contract. Key things that matter when editing:

- Each `<section>` that is a **direct child** of `<deck-stage>` is a slide. `data-label="NN Title"` is the speaker-facing label.
- Slides are authored at a fixed design size (**1920×1080**) and auto-scaled with `transform: scale()` to fit the viewport. Don't write responsive CSS — author at 1920×1080 and trust the scaler.
- Slides are **hidden, not unmounted** when inactive. State (videos, iframes, inputs) is preserved across nav.
- Keyboard: ←/→, PgUp/PgDn, Space, Home/End, number keys, `R` to reset.
- Current slide index persists in `localStorage` keyed by the document path — so refresh returns you to the slide you were on.
- Speaker notes are a single `<script type="application/json" id="speaker-notes">` array — one string per slide, indexed 0-based. Keep array length in sync with slide count (currently 30).

**Styling** uses `tokens.css` (design tokens: `--brand-orange`, `--flame-gradient`, `--font-display` = Space Grotesk, `--font-sans` = Geist, `--font-mono`, etc.) plus an inline `<style>` block at the top of the HTML with slide-specific utility classes (`.arch-block`, `.flow-card`, `.step`, `.alt-tab-chip`, `.time-chip`, `.flame-rule`, `.on-dark`, `.codeblock`, etc.). Prefer the existing utility classes before writing new inline styles.

## Editing conventions

- The `<!-- N TITLE -->` comment above each `<section>` is the canonical slide index. Keep it in sync with the footer page number (`NN / 30`) and the `data-label`.
- When adding a slide, update the **speaker-notes JSON array** (add a string at the matching index) and renumber all footer `NN / 30` values downstream.
- QR codes live in `assets/qr-*.svg` — regenerate via `/tmp/gen_qr.py` (uv inline-script, no install needed: `uv run /tmp/gen_qr.py`).
- Do **not** reintroduce the analogy vocabulary (Vitrina / Bodega / Cerebro / Cocina / Middleware). The deck uses the direct technical terms: **Frontend, Backend, Database, IA**. This was a deliberate editorial pass.

## Files

- `Automatizacion IA - Taller.html` — the deck (authored, edited here)
- `Automatizacion IA - Taller v1.html` — the original handoff version, do not edit
- `tokens.css` — design tokens
- `deck-stage.js` — the `<deck-stage>` web component (read top comment before modifying)
- `assets/` — logos, event imagery, QR codes
- `fonts/` — Geist + Space Grotesk variable fonts
- `uploads/prompt_presentacion_taller.md` — original content brief from the speaker
