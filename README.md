# Content Pilot

**By Demand Designer.** A single-file, browser-based tool that turns a long-form transcript into a full set of SEO-ready content assets: keyword plans, YouTube descriptions, podcast show notes, titles, learning bullets, meta tags, viral clip packages, and a video intro storyboard.

Content Pilot is a self-contained HTML file. It runs entirely in the browser, stores settings locally, and calls the AI provider of your choice with your own API key. It is built to be dropped into a Framer site as an HTML embed, but it works as a standalone page too.

---

## Features

- **Bring-your-own-key, multi-provider.** OpenAI (GPT-5.5), Anthropic (Claude Sonnet 4.6), or Google (Gemini 3.5 Flash). Models are current as of June 2026.
- **Three input modes.** Paste a transcript, upload a TXT / DOCX / SRT file, or pull a YouTube or Vimeo URL through a transcription webhook.
- **Brand intelligence.** Set your niche, paste or scrape your links and CTAs, and generate keyword and entity suggestions that the AI weaves into every asset.
- **Eight asset types** generated in one run, each as its own card.
- **Refine in place.** A per-asset chat lets you tweak any output ("make it shorter", "punchier hook") without regenerating everything.
- **Export.** Copy a single asset, copy the whole bundle, or download everything as a `.txt`.
- **Glassmorphic Demand Designer design system.** Warm monochrome base, glassmorphic orange-gradient accent, gradient blacks, depth-of-field shadows.
- **Accessible and responsive.** Labeled controls, keyboard-friendly modals (Escape and outside-click to close), an in-app How-to-use guide, and a layout that collapses cleanly to mobile.

---

## Quick start

1. Download or clone this repository.
2. Open `index.html` in any modern browser (no build step, no server required).
3. Click the gear icon to open **Settings**, choose your AI provider, paste your API key, and press **Authorize System**.
4. Add a transcript, choose your asset types, and press **Execute Full Synthesis**.

New to it? Open the **How to use** button in the header for a five-step walkthrough.

---

## Tech notes

- **No build step.** Plain HTML, CSS, and vanilla JavaScript in one file.
- **Dependencies** load from CDN at runtime: Tailwind CSS (utility classes), `mammoth.js` (DOCX parsing), and the Inter font. The brand font ABC Diatype is referenced first in the font stack and falls back to Inter where it is not licensed.
- **Storage.** Settings, keys, and your brand profile live in `localStorage` under the `content-pilot-config` key. Nothing is sent to any server except your chosen AI provider (and your own webhooks, if configured).
- **Brand scraper** uses the public AllOrigins proxy and may be blocked by some sites; pasting links manually is the reliable path.

---

## Security

API keys are stored in the browser and sent directly to the provider from the browser. This is fine for personal use on a trusted device. For shared or public deployments, route requests through a server-side proxy and use keys with spend limits. See [SECURITY.md](SECURITY.md) for the full picture.

---

## Publish this repository to GitHub

From inside this folder:

```bash
git init
git add .
git commit -m "Initial commit: Content Pilot 1.0.0"
git branch -M main
# create an empty repo named content-pilot on GitHub first, then:
git remote add origin https://github.com/<your-username>/content-pilot.git
git push -u origin main
```

Prefer the GitHub CLI? After `git commit`, run:

```bash
gh repo create content-pilot --private --source=. --push
```

## Deployment

- **Framer embed** and **GitHub Pages** instructions are in [docs/DEPLOY.md](docs/DEPLOY.md).
- A GitHub Actions workflow (`.github/workflows/pages.yml`) auto-publishes `index.html` to GitHub Pages on every push to `main`.

---

## Roadmap

- Functional Save / Load brand profiles (the selector is currently cosmetic).
- Optional serverless key proxy (Cloudflare Worker or Vercel function) to remove browser key exposure and CORS limits.
- Run history and persistence of generated assets.

See [CHANGELOG.md](CHANGELOG.md) for version history.

---

## License

Proprietary. All rights reserved by Demand Designer. See [LICENSE](LICENSE).
