# AI Solutions Applicable to Software Construction — A Rapid Multivocal Review

Research paper (UFRJ, 2025) by Felipe Assis, Júlio César Guimarães et al.

## About

This paper conducts a **Rapid Multivocal Review (RMR)** that systematically maps
Generative AI / LLM solutions applicable to **software construction**, drawing on
both academic and grey literature.

Using a **PICOC-based** search strategy and advanced filtering, the review identifies
**156 Generative AI tools** and categorizes them by usage context:

- general-purpose tools,
- frontend-only solutions, and
- full app-generation platforms.

For each, it assesses **maturity, accessibility, and limitations** beyond conventional
code generation, and discusses key challenges (context-awareness, integration and cloud
dependencies, data-privacy concerns) along with future directions.

**Keywords:** Generative Artificial Intelligence, Software Construction, Large Language
Model, AI Tool.

## Structure

The paper is written in LaTeX using the SBC Reviews class, under
[`SBC-Reviews-Class-Latex-v1.0/`](SBC-Reviews-Class-Latex-v1.0/):

| File | Section |
| --- | --- |
| `0-main-en.tex` | Main document (English) |
| `0-main-pt.tex` | Main document (Portuguese) |
| `1-introduction.tex` | Introduction |
| `2-related-work.tex` | Related work |
| `3-research-method.tex` | Research method |
| `4-results.tex` | Results |
| `5-discussion.tex` | Discussion |
| `6-future-work.tex` | Future work |
| `7-final-remarks.tex` | Final remarks |
| `8-acknowledgements.tex` | Acknowledgements |
| `9-refs.bib` | References (BibTeX) |

## Building

Compile the main document with `latexmk` (handles the pdflatex/BibTeX passes),
sending every generated file to a `build/` subfolder so the source tree stays clean:

```bash
cd SBC-Reviews-Class-Latex-v1.0
latexmk -pdf -outdir=build 0-main-en.tex
```

The final `0-main-en.pdf` (and all intermediates) land in
`SBC-Reviews-Class-Latex-v1.0/build/`, which is git-ignored.

To remove all build artifacts:

```bash
latexmk -C -outdir=build
```

### Editing in VS Code

The LaTeX Workshop output directory is preconfigured (`.vscode/settings.json`) to
the same `build/` folder, so builds from the editor stay out of the source tree too.

> **Overleaf note:** this project is also an Overleaf repository. Overleaf executes
> any committed `.latexmkrc`, and a custom `$out_dir` there breaks Overleaf's PDF
> preview. The `build/` redirection is therefore configured per-invocation
> (`-outdir`) and in editor settings only — there is intentionally no committed
> `.latexmkrc`. Overleaf compiles the paper with its own defaults, unaffected.
