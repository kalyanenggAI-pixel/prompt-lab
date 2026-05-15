# Prompt Lab

> A single-file, zero-dependency Claude prompt version manager and lightweight eval lab for AI builders.

## What problem it solves

Prompt iteration usually decays into `prompt_v1.txt`, `prompt_v2_final.txt`, and a lot of memory-based judgment. Prompt Lab keeps the working history in one place so you can:

- version prompts cleanly
- test them against realistic inputs
- compare outputs side by side
- preserve exactly what was run

## Features

- **Prompt versioning** — create, duplicate, tag, and archive prompt variants
- **Claude-native testing** — add one Anthropic API key and run prompts directly from the browser
- **Repeatable test cases** — define small suites of realistic inputs with optional expected phrases
- **Run snapshots** — every run stores the resolved prompt, variables, model, and settings used at that moment
- **Ratings + scoring** — rate outputs 1–5 and keep average scores per version
- **Side-by-side comparison** — compare outputs plus the underlying prompt/settings delta
- **Import / export** — move your lab as JSON without any backend
- **Offline-first structure** — one HTML file, no build step, no npm install, no external assets required

## Quickstart

Open `index.html` directly in your browser, then add an API key for the provider you want to use.

If your browser blocks local API requests from a file URL, serve the folder locally instead:

```bash
python -m http.server 8080
```

Then open `http://localhost:8080`.

## Why this is useful for AI builders

Exploration and evaluation are different jobs:

- use **Run** when you are still feeling out a prompt
- use **Run suite** when you want repeatable checks across known cases
- use **Compare** when you need to defend why one version is better than another

That division is the difference between a toy playground and a workflow you can actually trust.

## Security note

Prompt Lab stores API keys in browser `localStorage` and calls providers directly from the browser. That is acceptable for local development, but not for a public hosted deployment. If you later ship this beyond your own machine, add a backend and server-side secret handling first.

## Files

```text
index.html            # the full app
example-prompts.json  # starter data you can import
README.md             # project overview
```

## Roadmap ideas

- richer eval assertions beyond “expected phrase”
- CSV export for run analysis
- prompt diff highlighting
- dataset-level scorecards
- CI-triggered eval runs

## License

MIT
