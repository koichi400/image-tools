# Image Tools — Convert, Compress, Resize & Crop in Your Browser

Convert HEIC to JPG, compress, resize, rotate, and crop images entirely in your browser. Your files never leave your device.

A static web app with no backend and no database. Every operation runs 100% locally in the visitor's browser, so there are no uploads, no server costs, and no file-size limits imposed by a server.

## Features

- **Convert** — HEIC/HEIF to JPG, plus JPG / PNG / WebP format conversion
- **Compress** — Quality slider, plus automatic adjustment to a target file size (200 KB – 2 MB)
- **Resize** — Resize by longest edge, with rotation (90° steps)
- **Crop** — Drag / corner-handle crop modal with aspect-ratio presets (1:1, 4:3, 16:9, free, …), applied at full resolution before resize and compression
- **Batch** — Up to 50 images at once via drag & drop or paste, with before/after size summary, individual download or ZIP download
- **Presets** — One-click settings for official submissions, email attachments, SNS/blog, or plain conversion
- **Privacy** — EXIF metadata is stripped on export; images are never uploaded

## Libraries (loaded from CDN)

- [heic2any](https://github.com/alexcorvi/heic2any) — HEIC/HEIF decoding
- [JSZip](https://stuk.github.io/jszip/) — ZIP download for batch export

## Internationalization (i18n)

The UI is available in English, Japanese, and Thai, switchable with the **EN / 日本語 / ไทย** toggle in the top-right corner. On first visit the language is detected from the browser's language setting, and the chosen language is saved in `localStorage` so it persists on the next visit.

All user-facing strings are managed centrally in a single dictionary object (`I18N`, with `en`, `ja`, and `th` locales) in `index.html` — nothing is hard-coded in the markup or the logic. To add another language, add a locale object with the same keys.

## Deploy to Cloudflare Pages (free)

### Option A: GitHub integration (auto-deploy on push)

1. Push this folder to a GitHub repository
2. In the Cloudflare Dashboard, go to **Workers & Pages → Create → Pages → Connect to Git** and select the repository
3. Build settings:
   - Framework preset: `None`
   - Build command: *(leave empty)*
   - Build output directory: `/` (root)
4. Click **Save and Deploy** — the site goes live at `https://<project-name>.pages.dev`
5. Optional: attach a custom domain under **Custom domains** in the Pages project (e.g. `image.example.com`)

### Option B: Direct upload

In the Cloudflare Dashboard, go to **Workers & Pages → Create → Pages → Upload assets** and upload this folder (`index.html`).

### Option C: Wrangler CLI

```bash
npx wrangler pages deploy . --project-name image-tools
```

## Run locally

```bash
npx serve .
# or
python3 -m http.server 8000
```

Then open http://localhost:8000 in your browser.

## License

MIT — © 2026 Koichi Uemura. See [LICENSE](LICENSE).
