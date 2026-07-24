# Building `template.tex`

This document uses the MDPI IJMS LaTeX class (`Definitions/mdpi.cls`) with an
internal bibliography (`thebibliography`), so no separate `bibtex` pass is
required unless the references are changed to use an external `.bib` file.

## Requirements

- `pdflatex` (part of a standard TeX Live / MacTeX install)

## Build

Run from the `ijms_submission` directory:

```bash
pdflatex -interaction=nonstopmode -halt-on-error template.tex
pdflatex -interaction=nonstopmode -halt-on-error template.tex
```

Running it twice resolves cross-references, citations, and the table of
contents. The output is `template.pdf`.

If the bibliography is changed to use an external `.bib` file instead of the
inline `thebibliography` environment, add a `bibtex` pass:

```bash
pdflatex -interaction=nonstopmode -halt-on-error template.tex
bibtex template
pdflatex -interaction=nonstopmode -halt-on-error template.tex
pdflatex -interaction=nonstopmode -halt-on-error template.tex
```
