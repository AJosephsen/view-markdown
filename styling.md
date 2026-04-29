# Styling markdown with view-md

The viewer renders markdown into plain HTML inside a `#content` div. You can style any of it with a `viewer.css` file placed alongside your markdown files.

## How viewer.css is found

When you open a markdown file, the viewer looks for `viewer.css` starting in the same directory as the file, then walks up toward the root — using the first one it finds.

```
example.com/
  docs/
    viewer.css        ← applies to everything under /docs/
    guide.md
    api/
      reference.md    ← viewer.css in api/ would override the one in docs/
```

You can also force a specific stylesheet with the `?css=` parameter:

```
view-md.html?path=./guide.md&css=./custom.css
```

## Available CSS selectors

All rendered content lives inside `#content`. The viewer also exposes `#topbar` for the navigation bar.

### Text

| Selector | Element |
|---|---|
| `#content h1` | Top-level heading |
| `#content h2` | Section heading |
| `#content h3` | Sub-section heading |
| `#content p` | Paragraph |
| `#content a` | Link |
| `#content strong` | Bold text |
| `#content em` | Italic text |
| `#content blockquote` | Block quote |
| `#content hr` | Horizontal rule |

### Code

| Selector | Element |
|---|---|
| `#content code` | Inline code (backtick) |
| `#content pre` | Fenced code block |
| `#content pre code` | Code text inside a block |

### Lists

| Selector | Element |
|---|---|
| `#content ul` | Unordered list |
| `#content ol` | Ordered list |
| `#content li` | List item |

### Tables

| Selector | Element |
|---|---|
| `#content table` | Table |
| `#content th` | Header cell |
| `#content td` | Data cell |
| `#content tr:nth-child(even)` | Alternating row |

### Images

| Selector | Element |
|---|---|
| `#content img` | Image |

### Chrome

| Selector | Element |
|---|---|
| `#topbar` | Navigation bar at the top |
| `#content` | The content container itself |
| `body` | Page background |

## Useful patterns

### Dark code blocks

```css
#content pre {
  background: #0d1117;
  color: #e6edf3;
  border: none;
  border-radius: 10px;
}
#content pre code { color: #e6edf3; }
```

### Accent color for headings

```css
#content h2 {
  color: #3b6ff0;
  border-bottom: none;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  font-size: 0.95em;
}
```

### Styled inline code

```css
#content code {
  background: #eef2fd;
  color: #2952c4;
  border-radius: 4px;
  padding: 2px 5px;
}
```

### Wider or narrower content

```css
#content { max-width: 960px; }  /* wider */
#content { max-width: 620px; }  /* narrower, more readable */
```

### Sibling selectors (no classes in markdown)

Since markdown produces no CSS classes, sibling selectors are how you target specific patterns:

```css
/* Paragraph immediately after h1 (acts as a subtitle) */
#content h1 + p { color: #666; font-size: 1.1em; }

/* Paragraph after a horizontal rule (footer-style) */
#content hr + p { color: #999; font-size: 0.875em; }
```

## What you cannot do

- **Target specific paragraphs or headings by position** beyond simple sibling selectors — markdown produces no `id` or `class` attributes on text elements
- **Style syntax-highlighted code** — the viewer uses no syntax highlighter, code is plain text
- **Override the topbar layout** without also breaking navigation — the buttons use flexbox inside `#topbar`

---

→ [Back to index](index.md)
