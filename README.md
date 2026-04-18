# Tiger Transcribe

A fully offline dictation tool that runs entirely in your browser. No server, no account, no audio leaves your device.

**[Open the app](https://transcribe.taptiger.dev)**

---

## How it works

The first time you start dictation, the app downloads a ~128 MB speech model and caches it in your browser's IndexedDB. After that, it works completely offline — no internet connection required.

The app uses **Vosk (Kaldi/WebAssembly)** — a fully local speech recognizer compiled to WebAssembly. No audio ever leaves your device.

## Features

- **Dictation** — Start/stop with a button, keyboard shortcut, or spacebar
- **Editable transcript** — The dictation pad is fully editable; click anywhere to correct
- **Archive** — Past sessions are saved and can be restored, copied, or deleted
- **Custom dictionary** — Add words the model doesn't know; applied as a post-processing pass using phonetic matching
- **Macros** — Define phrases that expand to longer text on recognition
- **Floating window** — Pop out into an always-on-top Picture-in-Picture window while you work in another app
- **Dark/light theme**

## Keyboard shortcuts

| Shortcut | Action |
|---|---|
| `⌘/Ctrl` + `Shift` + `M` | Toggle mic (works anywhere on the page) |
| `Esc` | Stop dictation |
| `Space` (pad unfocused) | Start / Stop |
| `⌘/Ctrl` + `Shift` + `C` | Copy all text |
| `;;` | Insert today's date |

## Privacy

Vosk runs entirely in WebAssembly inside your browser. No audio is ever sent anywhere — not even on first load, only the model file is downloaded. No analytics. No telemetry. No accounts.

## Tech

- Single HTML file — no bundler, no framework, no build step
- [vosk-browser](https://github.com/ccoreilly/vosk-browser) for WebAssembly speech recognition
- Web Audio API + AudioWorklet for audio capture
- IndexedDB for dictionary, macros, and transcript persistence
- Deployed via GitHub Pages
