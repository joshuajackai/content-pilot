# Contributing

Content Pilot is proprietary to Demand Designer. External contributions are not
accepted without prior written permission. This guide is for authorized
collaborators.

## Project shape

The entire app lives in a single file: `index.html`. There is no build step and
no package manager. HTML, CSS (CSS variables plus Tailwind utility classes), and
vanilla JavaScript all live in that one file.

## Local development

1. Clone the repo.
2. Open `index.html` in a browser. That is the whole loop.
3. For quick local serving with correct relative paths, you can run any static
   server, for example: `python3 -m http.server` then open the printed URL.

## Conventions

- **Single file.** Keep everything in `index.html` so it stays a drop-in Framer embed.
- **Design tokens.** Colors, radii, shadows, and gradients are defined as CSS
  variables on `#cp-wrapper`. Reuse the tokens (`--cp-ink`, `--grad-orange`,
  `--sh-md`, and so on) rather than hardcoding values.
- **No pure black or white.** Use the warm off-black and off-white tokens.
- **No em dashes** in any user-facing copy.
- **Accessibility.** Keep labels on inputs, roles on tabs and dialogs, and
  keyboard support (Escape and outside-click close) intact.
- **IDs are wiring.** The JavaScript references elements by `id`. If you rename
  an `id`, update every reference.

## Before opening a pull request

- Confirm the JavaScript parses (no console errors on load).
- Check the full flow: add content, generate, refine, copy, export.
- Check desktop and mobile widths.
- Confirm provider model identifiers are current (they drift; see the
  `MODEL_MAP` near the top of the script).

## Commit style

Short, imperative commit messages, for example: `Add save profile persistence`,
`Fix mobile header wrap`, `Update Gemini model id`.
