# Compiling the paper

Main file: `paper.tex` (IUCr journal class). The appendix is pulled in via
`\input{paper_appendix.tex}`, and the bibliography is `paper_refs.bib`.

## Requirements

- A TeX distribution with `pdflatex` and `bibtex` (e.g. TeX Live or MacTeX).
- Everything else needed is already in this folder: `iucrjournals.cls`,
  `harvard.sty`, `iucr.bst`, `paper_refs.bib`, and `figs/`.

## Build

Run from inside this directory:

```bash
pdflatex -interaction=nonstopmode -halt-on-error paper.tex
bibtex paper
pdflatex -interaction=nonstopmode -halt-on-error paper.tex
pdflatex -interaction=nonstopmode -halt-on-error paper.tex
```

Two `pdflatex` passes after `bibtex` are needed to resolve citations and
cross-references. Output is `paper.pdf`.

## Cleaning up

Build artifacts (`*.aux`, `*.bbl`, `*.blg`, `*.log`, `*.out`, `*.pdf`, ...)
are git-ignored. To remove them:

```bash
rm -f paper.aux paper.bbl paper.blg paper.log paper.out paper.pdf
```
