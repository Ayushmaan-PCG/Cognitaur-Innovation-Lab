# Cognitaur Innovation Lab — Website

Official site for Cognitaur Innovation Lab, founded by Ayushmaan Bellum.
Plain HTML/CSS/JS — no build step, no frameworks, no dependencies.

## Project structure

```
cognitaur-site/
├── index.html                     ← the entire site (markup, styles, scripts)
├── README.md
└── assets/
    ├── img/
    │   ├── logo-cognitaur.jpg     ← full hero logo
    │   ├── mark-robot.jpg         ← square robot badge (nav + footer)
    │   ├── favicon.jpg
    │   ├── founder-ayushmaan.jpg
    │   ├── pillar-cnc.jpg
    │   ├── pillar-3dprinting.jpg
    │   ├── pillar-research.jpg    ← NHSJS paper first page (links to article)
    │   ├── invention-dermalytix.jpg
    │   ├── invention-robopyll.jpg
    │   └── invention-qrhealthx.jpg
    └── docs/
        └── Ayushmaan_Bellum_Resume.pdf
```

## Run locally

Option A — just open it: double-click `index.html`.

Option B — local server (recommended; matches production behavior):
- VS Code / Cursor: install the **Live Server** extension → right-click
  `index.html` → "Open with Live Server".
- Or from a terminal: `python3 -m http.server 8000` then visit
  http://localhost:8000

## Where things live in index.html

Everything is in one file, organized top to bottom:
- `<style>` block — all CSS. Design tokens (colors, fonts) are CSS variables
  under `:root` (`--ink`, `--brass`, `--steel`, etc.).
- Sections in order: nav → hero → #pillars (P-01…P-06) → #inventions →
  #founder → #camps → #register → #internships → #mentors → #media → #collab
  → footer.
- `<script>` at the bottom — mobile menu, scroll reveal, registration form.
  `CONTACT_EMAIL` is defined there (currently bellumayush@gmail.com).

## Remaining TODOs before launch

1. **Videos** — each pillar has a placeholder block marked with an HTML
   comment. For YouTube (Unlisted), replace the placeholder `<div class="ph">…</div>`
   with:
   `<iframe width="100%" style="aspect-ratio:16/9;border:0;border-radius:4px"
    src="https://www.youtube.com/embed/VIDEO_ID" title="…" allowfullscreen></iframe>`
   For local files, put e.g. `assets/video/cad.mp4` and use:
   `<video src="assets/video/cad.mp4" controls playsinline
    style="width:100%;border-radius:4px"></video>`
2. **Mentors** — four cards in #mentors contain [ bracketed ] placeholders for
   name, role, bio, and a 1:1 photo. Remove any unused cards.
3. **Add pillar photos** for CAD and Programming if desired (drop files into
   assets/img and swap the placeholder blocks the same way as the others).

## Deploy

Netlify / Vercel: drag the whole `cognitaur-site` folder into their dashboard.
GitHub Pages: push this folder to a repo → Settings → Pages → deploy from branch.
Then point the domain (cognitaur.com) at it per the host's DNS instructions.

All asset paths are relative, so the site works at any domain or subpath.
