# Using Content Pilot

A five-step walk from a raw transcript to a full set of publish-ready SEO assets.
This mirrors the in-app **How to use** guide.

## 1. Connect your AI provider

Open **Settings** (the gear, top right). Choose your Content Engine:

- OpenAI GPT-5.5
- Claude Sonnet 4.6
- Google Gemini 3.5 Flash

Paste your API key and press **Authorize System**. The key is stored only in
this browser. For shared or public use, route calls through a server-side proxy
(see SECURITY.md).

Where to get a key:

- OpenAI: https://platform.openai.com/api-keys
- Anthropic: https://console.anthropic.com
- Google AI Studio: https://aistudio.google.com/app/apikey

## 2. Provide your content

Pick one of the three tabs in **Provide Content**:

- **Paste** a transcript directly.
- **File** to upload a `.txt`, `.docx`, or `.srt` (timestamps are stripped from SRT).
- **URL** to pull a YouTube or Vimeo link. URL transcription posts to a
  transcription webhook you set in Settings (built with Make or Zapier) and
  expects a JSON response containing a `transcript` field.

## 3. Set your brand intelligence

- Enter your **Target Niche** (for example, "AI SaaS marketing").
- Paste your links and CTAs into the boilerplate box, or use the **Brand
  Scraper** to pull them from a URL (note: scraping uses a public proxy and may
  be blocked by some sites).
- Optionally run **Suggest Keywords** and **Extract Entities** to add SEO context
  the AI will fold into every asset.

## 4. Choose your assets and run

Tick the asset types you want:

- Keyword Plan
- YouTube Hub (description)
- Podcast Notes
- SEO Titles
- Learning Bullets
- Meta Tags
- Viral Clips
- Storyboard

Optionally fine-tune the per-asset AI directives in the **Advanced** panel, then
press **Execute Full Synthesis**. Each asset renders as its own card.

## 5. Refine, copy, and export

- **Refine** opens a small chat on any card. Type an instruction such as "make
  it shorter" or "punchier hook" and the card updates in place.
- **Copy Asset** copies one card.
- **Copy All Assets** copies the whole bundle.
- **Download .txt** saves everything as a single text file.

## Troubleshooting

- **"Set your API Key first"**: open Settings and authorize a provider.
- **API error**: the message shown comes from the provider. Common causes are an
  invalid key, no billing on the account, or a retired model id.
- **Network / CORS error**: some providers block direct browser calls. Try a
  different provider or set up a server-side proxy.
- **Transcription fails**: confirm your transcription webhook is set in Settings
  and returns JSON with a `transcript` field.
