# Final Year Internship Report Template

## Structure

```
.
├── main.tex                  # Master document
├── references.bib            # BibLaTeX bibliography
├── img/
│   ├── isec.png
│   └── company.png
└── src/
    ├── 00_acknowledgements.tex
    ├── 01_synopsis.tex
    ├── 02_abstract.tex
    ├── 03_abbreviations.tex
    ├── 04_introduction.tex
    ├── 05_context.tex
    ├── 06_state_of_the_art.tex
    ├── 07_methodology.tex
    ├── 08_implementation.tex
    ├── 09_results.tex
    ├── 10_conclusions.tex
    └── 11_appendices.tex
```

## Compilation

```bash
latexmk -pdf main.tex
```

## Customisation
- Replace `FirstName LastName` and `Student Number` in `main.tex`.
- Add your institution logos to `img/`.
- Fill in each chapter file inside `src/`.
