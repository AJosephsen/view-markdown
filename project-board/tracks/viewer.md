# Viewer

The single-file `view-md.html` markdown viewer and supporting bits (`viewer.css`, `libs/marked.umd.js`, default `index.md` landing).

## Current focus

Idle.

## Next steps

_Nothing queued._

## Key files

- `view-md.html` — the viewer (single self-contained file).
- `viewer.css` — default styling, auto-discovered by walking up from md file's dir.
- `libs/marked.umd.js` — marked v15 (MIT).
- `index.md` — default landing page.
- `index.html` — meta-refresh redirect to `view-md.html?path=./index.md`.

## Recent capabilities (from git log)

- Topbar default-collapsed, expand on toggle.
- Auto-discover `viewer.css` walking up directories.
- `?css=` parameter to override stylesheet.
- Relative `.md` links navigate within viewer.

## Usage

- `view-md.html?path=./file.md` — local relative path.
- `view-md.html?path=https://host/file.md` — cross-origin.
- Dev: `python3 -m http.server 8080` from repo root.

## Gotchas

- Cross-origin requires `Access-Control-Allow-Origin: *` on the remote (GH Pages / Netlify / Vercel / CF Pages OK by default).

## Work log

| Date | What was done |
|---|---|
| 2026-05-02 | Created project board (recipe applied). Seeded viewer + adhoc tracks. |

---

→ [Back to board](../board.md)
