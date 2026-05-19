# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Lebenslauf von Zelin Fan, geschrieben in LaTeX mit dem `moderncv`-Paket (`casual` style, `blue` color). The single source file `zelin-cv.tex` compiles to `zelin-cv.pdf`. Content is in German.

## Build

Requires a LaTeX distribution with `moderncv` installed (e.g., TeX Live, MiKTeX).

```bash
pdflatex zelin-cv.tex
```

## GitHub Actions / GitHub Pages

The workflow (`.github/workflows/generate-cv.yml`) automatically builds the PDF on push to `main` using `xu-cheng/latex-action@v3` and deploys it to GitHub Pages via the built-in Pages deploy actions.

- GitHub Pages source must be set to **GitHub Actions** in repo settings (one-time manual step).
- Published URL: `https://ricogu.github.io/zelin-cv/zelin-cv.pdf`

## Architecture

- **`zelin-cv.tex`** — The entire CV source. Uses `moderncv` `casual` style, `blue` color, `ngerman` babel, geometry at 0.86 scale.
- **`zelin.jpg`** — Bewerbungsfoto, referenced via `\photo[64pt][0.4pt]{zelin}`.
- **`Zelin CV.pdf`** — Original reference PDF (CVwizard.com), kept for reference only.
- **`.github/workflows/generate-cv.yml`** — CI pipeline: builds LaTeX → cleans aux files → deploys PDF to GitHub Pages.

## Branches

- **`main`** — Source branch. All edits happen here.
- **`gh-pages`** is NOT used; deployment goes through the new GitHub Pages Actions flow directly.

## Editing Notes

- The CV is in German. Section names: `Berufserfahrung`, `Ausbildung`, `Sonstiges`, `Sprachkompetenz`, `Computerkompetenz`, `Qualifikationen`.
- To update the photo: replace `zelin.jpg` at repo root with a new JPEG/PNG, keeping the same filename.
- Do not commit `*.aux`, `*.log`, `*.out` — they are in `.gitignore`.
