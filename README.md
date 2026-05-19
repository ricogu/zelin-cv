# zelin-cv

Lebenslauf von Zelin Fan, geschrieben in LaTeX mit dem `moderncv`-Paket.

## Lokales Bauen

Voraussetzung: TeX Live oder MiKTeX mit `moderncv`.

```bash
pdflatex zelin-cv.tex
```

Das erzeugt `zelin-cv.pdf` im selben Verzeichnis.

## Veröffentlichung (GitHub Pages)

Der GitHub Actions Workflow (`.github/workflows/generate-cv.yml`) baut das PDF automatisch bei jedem Push auf `main` und stellt es auf GitHub Pages bereit.

**Einmaliger Setup-Schritt** (muss manuell im GitHub-Repo-Settings gemacht werden):

1. Gehe zu: `https://github.com/ricogu/zelin-cv` → **Settings** → **Pages**
2. Unter **Source**: wähle **GitHub Actions**
3. Speichern

Danach wird das PDF nach jedem Push automatisch unter folgender URL veröffentlicht:

> **https://ricogu.github.io/zelin-cv/zelin-cv.pdf**

## Dateistruktur

```
zelin-cv/
├── .github/
│   └── workflows/
│       └── generate-cv.yml   # CI: LaTeX bauen + GitHub Pages deployen
├── zelin-cv.tex              # LaTeX-Quelle
├── zelin.jpg                 # Bewerbungsfoto
├── Zelin CV.pdf              # Original-Referenz-PDF
├── .gitignore
├── CLAUDE.md
└── README.md
```

## Bearbeitung

Alle Änderungen am Lebenslauf werden in `zelin-cv.tex` vorgenommen. Nach einem `git push` auf `main` läuft die CI automatisch und aktualisiert das veröffentlichte PDF.
