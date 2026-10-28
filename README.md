# wave7t.github.io

Source of <https://wave7t.github.io> — a single static page.
No build step, no JavaScript, no dependencies: the repository root *is* the site.

```
index.html            the whole page
assets/css/site.css   all styling (aurora background, glass cards, responsive, print)
assets/img/           portrait.jpg (3:4) and favicon.svg
.nojekyll             tell GitHub Pages to serve files as-is
```

## Editing

Everything lives in `index.html`, top to bottom:

1. **Identity card** — name, affiliation, one-line positioning, Email / Scholar / GitHub, interest chips.
2. **About** — a short paragraph.
3. **Publications** — one list, no authorship sections; the abstract of each paper sits behind a `<details>` toggle:

```html
<li>
  <a class="pub-title" href="https://doi.org/…">Paper title</a>
  <p class="pub-authors">A. Author, <strong>Teng Wan</strong>, B. Author</p>
  <p class="pub-venue">Venue (ABBREV), year</p>
  <details>
    <summary>Abstract</summary>
    <p>Two or three sentences.</p>
  </details>
</li>
```

4. **Education**, **Experience** — one row per entry: years, role or degree, and one line of context.

Colours, spacing and the background glow are the CSS variables at the top of
`assets/css/site.css` (`--bg`, `--ink`, `--accent`, `--glass`, `--radius`, `--maxw`); the
three blurred shapes are `.orb--1/2/3` in the `.aurora` block.

## Publishing

GitHub Pages serves this repository's `main` branch at <https://wave7t.github.io>.

```bash
# preview locally
open index.html                     # or: python3 -m http.server 8000

# publish
git add -A && git commit -m "Update page" && git push
```

Changes usually appear within a minute. If they do not, check
**Settings → Pages** to confirm the source is `main` / root.
