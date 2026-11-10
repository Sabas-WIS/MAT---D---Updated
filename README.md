# MAT hub (Mortgage AI Toolkit)

Booth hub that opens an interactive demo for each product. Static site: no build step, no dependencies.

## Deploy on GitHub Pages
1. Upload the contents of this folder to the repository root, **including the `demos`, `assets` and `src` folders** (drag the folders themselves into the GitHub upload page, not only the loose files).
2. Settings > Pages > Deploy from a branch > pick the branch and `/ (root)`.
3. Open the Pages URL. The hub works offline after the first visit.

## Run locally
The demos are loaded with `fetch`, so use a local web server:

    python3 -m http.server 8080

then open http://localhost:8080. For a double-click version, use the single-file edition (`MAT-hub-single-file.html`).

## Structure
| Path | What it is |
|---|---|
| `index.html` | Hub shell (minified). Readable copy: `src/index.unminified.html` |
| `demos/<product>.html` | One self-contained demo per product |
| `assets/img/` | Logos, QR code and favicon |
| `assets/clips/` | Collibry participant clips, loaded only when Collibry is opened |
| `sw.js` | Service worker: caches everything for offline use |

## Updating a demo
Replace the matching file in `demos/` (keep the file name). Then change `const VER` in `sw.js` (for example to `mat-hub-v2`) so booth devices pick up the new files.
