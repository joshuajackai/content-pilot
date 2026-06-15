# Deploying Content Pilot

Content Pilot is a single static file (`index.html`). It can be hosted anywhere
that serves static files, and it embeds cleanly into Framer.

## Option A: GitHub Pages (included workflow)

This repo ships with `.github/workflows/pages.yml`, which publishes `index.html`
to GitHub Pages automatically.

1. Push this repo to GitHub.
2. In the repo, go to **Settings > Pages**.
3. Under **Build and deployment > Source**, choose **GitHub Actions**.
4. Push to `main` (or run the workflow manually from the **Actions** tab). The
   workflow deploys the site and prints the public URL.
5. Your tool will be live at `https://<your-username>.github.io/<repo-name>/`.

## Option B: Embed in Framer

Framer renders custom HTML inside an iframe, which is exactly how Content Pilot
is designed to run.

1. In Framer, add an **Embed** element (Insert > Embed, or the HTML embed
   component).
2. Choose the **HTML** option and paste the full contents of `index.html`, or
   point the embed at your hosted URL from Option A.
3. Set the embed to **100% width**.
4. Give the embed a **generous fixed height** or enable auto-height. The tool is
   tall (input column plus a results feed), so a short iframe will clip the
   lower cards. If your content grows, increase the height.
5. Publish and test on both desktop and a real phone. The layout collapses to a
   single column when the embed is narrow.

### Framer notes

- The embed inherits the iframe width, not the browser width, so test
  responsiveness by viewing the published page on a phone (or by narrowing the
  embed in the Framer canvas).
- `localStorage` works inside the Framer iframe, so saved settings persist per
  visitor per browser.

## Option C: Any static host

Upload `index.html` to Netlify, Vercel, Cloudflare Pages, S3, or any static host.
No build step is required.

## After deploying

- Open the page, add your API key in Settings, and run one synthesis to confirm
  the full path works end to end.
- If you plan to share the page publicly, read SECURITY.md and consider a
  server-side key proxy before going live.
