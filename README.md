# Polyglot — Code Converter

A browser-based code translation utility that rewrites source code from one language into another using Groq's chat completions API. It streams token-by-token output, auto-detects the source language heuristically, performs round-trip verification and optional execution comparison via Piston (emkc.org), and supports batch conversions and downloads.

This repository contains a single-file web app (code-converter.html) that runs entirely in your browser — no server component is required. Your GROQ API key is used directly from the browser to call Groq's API and is not stored server-side.

Features

- Paste or upload source files and convert them to a chosen target language
- Auto-detect source language, streaming output, and explain mode (notes for risky/unequal conversions)
- Syntax highlighting with Prism, JS parsing with Acorn, and batch download via JSZip
- Round-trip verification (convert back and diff) and optional run & compare using Piston
- Multi-file batch conversions and download as a ZIP

Quickstart

1. Open code-converter.html in a modern browser (double-click the file or serve it from a local static server).
2. Add your GROQ API key in the "GROQ_API_KEY" field (get a free key at https://console.groq.com/keys).
3. Paste code into the left pane or upload files, choose the target language, and click the Convert button (or press ⌘/Ctrl + Enter).
4. Review the converted code on the right. Use Verify to perform a round-trip diff, or Run & compare to execute both versions and compare output.

Notes and security

- The app calls Groq's API directly from the browser using the API key you provide — do not paste secrets or private keys into code you plan to convert.
- The "Run & compare" feature sends code to Piston (emkc.org) for execution; do not run untrusted code containing secrets or production data.
- Heuristic checks and auto-detection are not a substitute for manual review. Always read generated code before running it.

Files

- code-converter.html — the single-file web app (UI + JS + styles)
- README.md — this file
- USAGE.md — user-facing operating notes and UI guide
- LICENSE — MIT

Contributing

If you'd like to propose changes, open an issue or submit a pull request. Small fixes, documentation improvements, and bug reports are welcome.

License

This project is available under the MIT License. See the LICENSE file for details.
