# Report

The written deliverables for the project, in English.

| File | What it is |
|------|------------|
| [`FULBO-paper.pdf`](FULBO-paper.pdf) | The full report: data, methodology, results and analysis, conclusions. |
| [`FULBO-poster.pdf`](FULBO-poster.pdf) | A1 poster summarising the pipeline and the headline numbers. |
| [`paper/`](paper/) | LaTeX source of the paper, including every figure. |

## Building the paper

The source lives in [`paper/`](paper/) and compiles with a standard TeX Live
installation. From this directory:

```bash
cd paper
latexmk -pdf main.tex
```

Without `latexmk`, the equivalent is:

```bash
cd paper
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

`FULBO-paper.pdf` in this directory is the output of that build, downsampled to
200 dpi to keep the repository light.

## Source layout

```
paper/
├── main.tex          document skeleton, loads everything else
├── preamble.tex      packages
├── settings.tex      title, authors, colours, headings, headers
├── references.bib    bibliography
├── sections/
│   ├── 00-titlepage.tex
│   ├── 01-introduction.tex
│   ├── 02-data.tex
│   ├── 03-methods.tex
│   ├── 04-results.tex
│   └── 05-conclusion.tex
└── figures/          every figure used by the report
```

The numbers reported in the paper are the ones stored under
[`../models/`](../models/) and
[`../src/evaluation/keypoints/evaluation_outputs/`](../src/evaluation/keypoints/evaluation_outputs/).
