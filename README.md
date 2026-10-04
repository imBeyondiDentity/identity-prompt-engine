# iDentity Prompt Engine — Music DNA

[Русская версия](README_ru.md)

A browser-based tool for building structured Suno AI music prompts from a library of composable "DNA" presets, genre bases and emotional-intensity sliders. Bilingual (English/Russian), fully static, no backend, no dependencies — everything runs client-side.

**Live:** https://imbeyondidentity.github.io/identity-prompt-engine/

## What it does

Tick DNA presets across eleven instrument/atmosphere families, pick a genre base, and set five emotional sliders. The engine compiles the selections into a ready-to-paste Suno prompt. The same selections also drive three other outputs: a lyric brief, a MDL tag dump, and an independent text Humaniser.

## Features

- **78 DNA presets across 11 families** — Atmosphere/World, Guitar, Keys, Strings, Brass, Synth Lead, Drums, Bass, Flow, Vocal, Dynamics. Each preset is tick-to-add.
- **24 genre bases in three groups** — Rock World (8), Ethno World (6), Beyond Rock (10).
- **Five emotional sliders** — Energy, Darkness, Mysticism, Aggression, Hope — shape both the prompt's tone and the generated lyric brief.
- **Four output tabs** — Suno prompt, Lyric brief, Humaniser, MDL (raw tag syntax) — each with its own one-click copy button.
- **Built-in Humaniser** — strips AI-writing markers (filler openers, em-dash overuse, bureaucratic phrasing, promotional language) from any pasted text, independently of prompt generation.
- **Saved presets** — name and store a DNA/genre/slider combination locally in the browser (`localStorage`); load or delete it later. No account, no server.
- **Bilingual interface** — a language-picker landing page routes to a fully separate English or Russian build of the engine.

## Usage

1. Open the live link above, or `index.html` locally, and pick a language.
2. Choose a genre base (Rock World / Ethno World / Beyond Rock).
3. Tick DNA presets across the eleven families.
4. Adjust the five emotional sliders.
5. Switch between the four output tabs and copy the result into Suno.

## Running locally

The engine is fully static — no build step, no dependencies. Either:

- open `index.html` directly in a browser, or
- serve the folder so links resolve the same way they do on GitHub Pages:

```bash
python3 -m http.server 8000
```

then visit `http://localhost:8000`.

## Publishing to GitHub Pages

1. Repository **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Branch: `main`, folder: `/ (root)`. **Save**.
4. The site goes live at `https://<your-username>.github.io/<repo-name>/` within a couple of minutes.

## Structure

```
index.html   language-picker landing page
en.html      English interface — full engine logic and DNA/genre data
ru.html      Russian interface — full engine logic and DNA/genre data
```

`en.html` and `ru.html` are each self-contained (markup, styles and logic in one file) and carry the same feature set and DNA/genre library independently — there is no shared JavaScript file between them.

## Limitations

- **No backend.** Saved presets live only in the browser's `localStorage`: they don't sync across devices or browsers, and clearing site data removes them.
- **No build pipeline in this repository.** Edits are made directly in `en.html` / `ru.html`.
- **Text output only.** The engine produces a prompt/brief/tag text — it doesn't call the Suno API or generate audio itself; the result is pasted into Suno manually.

## Licence

All rights reserved. © 2026 BeyondiDentity.

This source is published for reference and portfolio purposes. No open-source licence is granted; reuse, redistribution or commercial use requires prior written permission from the author.
