# view-md

A single-file drop-in markdown viewer for the browser.

Drop `view-md.html` and `libs/marked.umd.js` next to your markdown files and open:

```
view-md.html?path=./your-file.md
```

No build step. No config. No framework. Works on GitHub Pages.

## Features

- Renders any `.md` file via `?path=` URL parameter
- Relative `.md` links between files work automatically
- Back / forward navigation
- Cross-origin URLs supported (CORS permitting)
- Default landing page: place `index.md` next to `view-md.html`

## Quick start

```bash
git clone https://github.com/AJosephsen/view-markdown.git
cd view-md
python3 -m http.server 8080
# open http://localhost:8080/view-md.html
```

## Cross-origin usage

```
https://ajosephsen.github.io/view-markdown/view-md.html?path=https://your-site.com/notes.md
```

The remote file must have `Access-Control-Allow-Origin: *` (GitHub Pages, Netlify, Vercel, Cloudflare Pages do this by default).

## Files

| File | Purpose |
|---|---|
| `view-md.html` | The viewer (single self-contained file) |
| `libs/marked.umd.js` | [marked v15](https://github.com/markedjs/marked) — MIT |
| `index.md` | Default landing page |

## License

MIT

---

→ [Full usage guide & docs](index.md)
