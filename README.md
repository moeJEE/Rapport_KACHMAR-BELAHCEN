# Installation locale LaTeX

Ce projet utilise pdflatex + Biber (biblatex). Suivez ces étapes pour configurer un environnement LaTeX fonctionnel sur votre machine.

- **Windows (recommandé)**
    - Installer MiKTeX (Installer MiKTeX depuis le site officiel). Pendant l'installation, activez "Install missing packages on the fly" si proposé.
    - Vérifier que le dossier `MiKTeX\miktex\bin` (ou équivalent) est dans la variable `PATH` si vous souhaitez lancer `pdflatex` depuis le terminal.

- **macOS / Linux**
    - Installer TeX Live (ou MacTeX sur macOS) via le gestionnaire de paquets ou l'installateur officiel.

- **VS Code**
    - Installer l'extension LaTeX Workshop.
    - Exemple de réglages utiles (à placer dans `.vscode/settings.json` si nécessaire) :

```json
{
    "latex-workshop.latex.recipes": [
        {
            "name": "pdflatex x3",
            "tools": ["pdflatex", "pdflatex", "pdflatex"]
        }
    ],
    "latex-workshop.latex.recipe.default": "pdflatex x3",
    "latex-workshop.latex.clean.method": "glob"
}
```

- **Commandes de compilation (terminal)**
    - Depuis la racine du projet :

```bash
pdflatex -interaction=nonstopmode main.tex
biber main
pdflatex -interaction=nonstopmode main.tex
pdflatex -interaction=nonstopmode main.tex
```

- **Remarques et dépannage**
    - Si `biber` signale des clés manquantes, vérifiez `references.bib` et relancez `biber` puis `pdflatex` deux fois.
    - Si LaTeX Workshop tente d'utiliser `latexmk` mais que vous n'avez pas Perl installé, choisissez la recette `pdflatex x3` comme ci‑dessus.
    - Pour installer des paquets manquants sur Windows, ouvrez MiKTeX Console et installez les packages requis.
    - Si la référence à `LastPage` ou d'autres cross‑references sont incorrectes, exécutez `pdflatex` plusieurs fois jusqu'à stabilisation.

Si vous voulez, je peux ajouter automatiquement la configuration `.vscode/settings.json` utilisée dans ce dépôt ou lancer une compilation test locale maintenant. 

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
