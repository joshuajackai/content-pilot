# Changelog

All notable changes to Content Pilot are documented here. This project follows
a simple, human-readable changelog style.

## [1.0.0] - 2026-06-15

First public repository release.

### Added
- Header rebrand to **Content Pilot** with a "by Demand Designer" lockup.
- **How to use** header button opening an accessible accordion guide (five steps).
- Demand Designer design system: warm monochrome base, glassmorphic orange-gradient accent, gradient blacks, depth-of-field shadows, tokenized via CSS variables.
- Empty state and an explicit "nothing was generated" error state for the output feed.
- Live transcript character counter.
- Security and CORS notice in Settings.
- YouTube / Vimeo URL validation before transcription.
- Hardened AI request handling: real provider error messages, tolerant JSON parsing, CORS-aware network errors.
- Wired previously inactive controls: Transcribe (validate plus webhook), Extract Entities, Download .txt, and saving of all webhook fields.

### Changed
- Replaced placeholder model identifiers with the current June 2026 lineup: OpenAI `gpt-5.5`, Anthropic `claude-sonnet-4-6`, Google `gemini-3.5-flash`.
- Accessibility pass: labeled controls, ARIA roles on tabs and dialogs, keyboard-friendly modals (Escape and outside-click to close, focus return).
- Responsive pass: header wraps, asset grid and columns collapse cleanly to a single column on mobile.

### Known limitations
- Save / Load brand profile selector is present but not yet functional.
- API keys are stored in the browser; a server-side proxy is recommended for shared or public use.
