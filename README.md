# R12 Fieldday

Astro-Webseite fuer den Fieldday und die aktuellen Aktivitaeten des DARC Ortsverbandes R12. Basis ist das Theme `chrismwilliams/astro-theme-cactus`, angepasst fuer deutsche Inhalte, Blog, Tags, RSS, statische Suche und Netlify.

## Inhalte

- Startseite: `src/pages/index.astro`
- Fieldday-Seite: `src/pages/fieldday.astro`
- Projektliste: `src/pages/projekte.astro`
- Blogposts: `src/content/post/*.md`
- Tag-Beschreibungen: `src/content/tag/*.md`
- Impressum: `src/pages/impressum.astro`
- Datenschutz: `src/pages/datenschutz.astro`

## Markdown-Frontmatter

```md
---
title: "Titel des Beitrags"
description: "Kurze Beschreibung fuer Suche, RSS und SEO."
publishDate: 2026-05-17
tags: ["fieldday", "r12"]
pinned: false
---
```

Neue Tags funktionieren automatisch. Optional kann zu einem Tag eine Datei in `src/content/tag/` angelegt werden, zum Beispiel `fieldday.md`.

## Entwicklung

Die aktuelle Theme-Version benoetigt Node 22.12.0 oder neuer. Netlify ist in `netlify.toml` entsprechend konfiguriert.

```bash
pnpm install
pnpm dev
pnpm build
pnpm postbuild
```

`pnpm build` erzeugt die statische Seite in `dist/` und startet danach automatisch `postbuild` fuer den Pagefind-Suchindex.

## Deployment

Netlify:

- Build command: `pnpm build`
- Publish directory: `dist`
- Node: `22.12.0`
- pnpm: `10.23.0`

Die finale Domain muss vor dem Livegang in `src/site.config.ts` unter `url` eingetragen werden.
