# Security

## How keys are handled

Content Pilot is a client-side tool. When you enter an API key in Settings, it is:

- stored in the browser via `localStorage` (key name `content-pilot-config`), and
- sent directly from the browser to the AI provider you selected.

No key is ever sent to Demand Designer or any other intermediary. The same applies to any transcription or automation webhook URLs you configure.

## What this means in practice

- **Personal use on a trusted device is fine.** Your key stays on your machine.
- **Shared, kiosk, or public deployments are not recommended as-is.** Anyone with access to the device or browser profile can read the stored key, and browser-origin requests to some providers can be blocked by CORS.

## Recommended hardening for production

1. **Use a server-side proxy.** Route AI requests through a small serverless function (for example a Cloudflare Worker or Vercel function) that holds the key server-side. The browser then never sees the key, and CORS is resolved.
2. **Scope and cap your keys.** Use provider keys restricted to the needed models with spending limits enabled.
3. **Rotate keys** that may have been exposed on a shared machine.

## Never commit secrets

API keys must never be committed to this repository. The `.gitignore` excludes common secret files (`.env`, `*.local`, `secrets.json`). If a key is ever committed, rotate it immediately and purge it from git history.

## Reporting a vulnerability

If you discover a security issue, please contact Demand Designer directly rather than opening a public issue.
