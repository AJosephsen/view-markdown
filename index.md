# view-md

A single-file drop-in markdown viewer for the browser.

## Usage

### Serve any local markdown files

Drop `view-md.html` and `libs/marked.umd.js` into any directory you're serving statically, then open:

```
view-md.html?path=./your-file.md
```

### View a remote markdown file (CORS-enabled origins)

```
https://ajosephsen.github.io/view-markdown/view-md.html?path=https://example.com/readme.md
```

The linked file must be served with `Access-Control-Allow-Origin: *` (GitHub Pages, Netlify, Vercel, Cloudflare Pages all do this by default).

### Default landing page

Place an `index.md` next to `view-md.html` — it loads automatically when no `?path=` is given, and the home button (⌂) always returns to it.

## Features

- Single HTML file — no build step, no config, no framework
- Renders relative `.md` links so you can navigate between files
- Back / forward buttons track history correctly
- Works hosted on GitHub Pages or any static server

## Files

| File | Purpose |
|---|---|
| `view-md.html` | The viewer |
| `libs/marked.umd.js` | [marked v15](https://github.com/markedjs/marked) — MIT licensed |
| `index.md` | This page (default landing) |

## Docs

- [Styling markdown with viewer.css](styling.md)
- [README](README.md)
