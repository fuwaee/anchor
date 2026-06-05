# ⚓ Anchor

A single-page "megathread" listing useful & safe links, with content fully decoupled from code.

## How it works

- **`index.html`** — the whole site (dark mode, responsive cards, hover effects). It uses `fetch("links.json")` to load the data and renders one section per category automatically.
- **`links.json`** — the content. Edit this file to update the site; no HTML changes needed.

## Editing content

`links.json` is an array of categories:

```json
[
  {
    "category": "🎮 Video Games (Repacks)",
    "sites": [
      { "nom": "FitGirl Repacks", "url": "https://fitgirl-repacks.site/", "desc": "Torrent-based — use a VPN." }
    ]
  }
]
```

Each site has `nom` (name), `url`, and `desc` (description).

- The site **name is the clickable link** (opens in a new tab). Leave `desc` empty (`""`) to hide the description line.
- Any category whose name contains `❌` is rendered as a **blacklist**: red styling, a `⚠️ Avoid` badge, and no clickable link (so banned entries can't be opened).

## Running locally

It's a static site — open `index.html` through any web server (needed for `fetch` to work), e.g.:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/
```

## Deploying

Deploy the two files to any static host (GitHub Pages, Cloudflare Pages, Netlify, …). No build step required.
