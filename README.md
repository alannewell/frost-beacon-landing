# Frost BEACON™ — landing

Static marketing site. **No build step, no CDN, no dependencies.** Every asset is
served from this folder.

## Structure

```
frost/
├── index.html            # the page (all content lives here)
├── favicon.svg
├── robots.txt
└── assets/
    ├── css/
    │   ├── styles.css     # all styling (hand-written, no framework)
    │   └── fonts.css      # @font-face declarations -> assets/fonts/
    ├── js/
    │   └── main.js        # nav state, scroll-reveal, hero canvas, inline icons
    ├── fonts/             # Barlow / Inter / JetBrains Mono (woff2, latin subset)
    └── img/
        └── logo.png       # Frost & Sullivan — Brand and Demand Solutions lockup
```

## Deploy

Upload the whole `frost/` folder to any static host (Nginx, Apache, S3,
Netlify, GitHub Pages, cPanel…). No server-side code required.

- Serve `.woff2` with `Content-Type: font/woff2` (most servers already do).
- If it lives in a subdirectory, `index.html` uses **relative** paths so it works
  anywhere; `404.html` uses root-absolute paths — adjust if not at the domain root.

## Editing

- **Text / sections** → `index.html` (each section is commented).
- **Colours, spacing, type** → CSS custom properties at the top of `styles.css`.
- **Icons** → add the Lucide SVG path(s) to the `ICONS` map in `main.js`, then use
  `<span class="ico ico-15" data-icon="your-name"></span>`.

## Notes

- Fonts are the `latin` subset only. Add more subsets in `assets/fonts/` +
  `fonts.css` if you need extended characters.
- Reproduced from the original Figma Make prototype (`FROST BEACON LANDING`).
