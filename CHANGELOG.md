# Changelog

All notable changes to this project are documented here. The format is based on
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to
[Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.2.0] — 2026-08-19

See what cleanup actually changed, read scans more reliably, and use AI cleanup without guessing the wrong provider.

### Added

- **Changes tab:** after rule-based or AI cleanup, see what was added or removed, line by line, with a running added/removed count.
- **Pick your AI provider** in Diagnostics (DeepSeek, OpenAI, Groq, OpenRouter, or any compatible endpoint), then Test the key before you spend it. OpenAI and DeepSeek keys both start with `sk-`, so those you pick yourself; other prefixes switch automatically.
- Drop **plain text and Markdown** the same way you drop a PDF.
- A banner when a file converted to nothing usable, instead of a blank preview.
- While you drag a file over the window, a chip shows the detected type.
- **Ctrl+C** with nothing selected copies the full Markdown.
- Conversion errors say what went wrong (damaged PDF, unsupported type, empty extract) instead of dumping a traceback.

### Changed

- **Better conversion** for PowerPoint charts, SVG, and Word equations.
- **Better OCR for scans** — newer on-device engine, sharper page images. Models still ship in the install; nothing extra to download, nothing sent to the cloud.
- JSON and XML show as fenced code in Preview, so they don't get treated as prose.

**Already on 0.1.0?** Reinstall OCR from Diagnostics once. The old OCR package will not pick this up on its own.

## [0.1.0] — 2026-06-19

First public release. Windows, portable (extract-and-run; no installer).

### Added

- Convert PDF, DOCX, PPTX, XLSX, EPUB, HTML, CSV, JSON, and XML to clean Markdown, built on
  Microsoft's MarkItDown.
- **Cleanup modes:** Off, deterministic rule-based, and an optional AI pass (local Ollama or
  bring-your-own-key OpenAI-compatible / Anthropic).
- **OCR** for scanned PDFs and images (RapidOCR) and **audio transcription** (faster-whisper),
  installed on demand as optional engines.
- **Batch conversion** with adaptive concurrency, cancel, timeouts, and per-file progress.
- **Output control:** folder rules, naming templates, before/after preview.
- Self-provisioning Python 3.12 runtime on first launch; fully offline thereafter.
- First-run setup shown as a multi-step stepper with live download size/speed.

### Security

- Dependencies are integrity-verified during the one-time setup, so first run is trustworthy. See
  [`SECURITY.md`](SECURITY.md).

[0.2.0]: https://github.com/ibrahimqureshae/mdflux/releases/tag/v0.2.0
[0.1.0]: https://github.com/ibrahimqureshae/mdflux/releases/tag/v0.1.0
