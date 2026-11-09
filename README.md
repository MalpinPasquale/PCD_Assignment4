# PCD Assignment 4: Application Summary and Feature Selection

The current submission is an **English-language conceptual report in IEEE two-column format**, with no coding requirement and no experimental performance claims. It summarizes five application cases and explains suitable image features, possible techniques, and limitations.

## Current submission

- **[PCD_Assignment4.pdf](PCD_Assignment4.pdf)** — final report to submit.
- [PCD_Assignment4.tex](PCD_Assignment4.tex) — editable LaTeX source.
- [references.bib](references.bib) — bibliography.

| Case | Suitable features |
|---|---|
| Object counting | Intensity, area, circularity, centroid |
| Scanned-document enhancement | Local intensity, contrast, stroke width |
| Visible fruit ripeness | Hue, saturation, color-region ratios, spots |
| Surface-defect inspection | Gradient, elongation, variance, GLCM texture |
| Impulse-noise removal | Extreme intensity, deviation from local median |

Two original sample images illustrate typical input conditions; the report does not show or claim experimental outputs. Image credits are recorded in `images/SOURCES.md`.

**Author:** Malvino Rosana Pasquale  
**Student number:** 25/569865/PA/24015

Follow your course's rules on assistance and attribution.

### Compile the current report

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=build PCD_Assignment4.tex
cp build/PCD_Assignment4.pdf PCD_Assignment4.pdf
```

### Submission links

- Repository: https://github.com/MalpinPasquale/PCD_Assignment4
- **Current PDF:** https://github.com/MalpinPasquale/PCD_Assignment4/blob/main/PCD_Assignment4.pdf

---

## Previous version — optional material, not the current assignment

The files and instructions below belong to the earlier coding-based version. They are retained for reference only. **Submit `PCD_Assignment4.pdf`, not `main.pdf`; no notebook needs to be run or submitted for the revised assignment.**

### Previous-version files

- [`main.pdf`](main.pdf): previous experimental report, superseded by `PCD_Assignment4.pdf`.
- [`digital_image_processing_cases.ipynb`](digital_image_processing_cases.ipynb): explanations, simple Python code, figures, and actual execution outputs.
- [`main.tex`](main.tex) and [`references.bib`](references.bib): editable report source and references.
- `images/`: original sample images and attribution information.
- `figures/`: generated comparison figures used in the report.
- `results/metrics.json`: measured features and evaluation results.
- `IEEEtran.cls` and `IEEEtran.bst`: original IEEE LaTeX class and bibliography style from CTAN; their upstream licensing headers are retained.

**Before submission:** replace `Student Name` and `University / Department` in `main.tex` with your own details and recompile. Read the notebook and understand the methods, assumptions, and limitations. Follow your course's rules on assistance and attribution.

## Cases and features

| Case | Simple methods | Suitable features |
|---|---|---|
| Coin counting | Gaussian smoothing, Otsu thresholding, morphology, labeling | Intensity, area, centroid, circularity |
| Document enhancement | Global vs. local thresholding | Local intensity/contrast, text fraction, component size |
| Impulse-noise removal | Gaussian vs. 3 × 3 median filter | Extreme intensity and neighborhood consistency; MSE/PSNR for reference evaluation |

The actual coin count is **21**, compared with **24** manually counted coins. This baseline is intentionally discussed honestly rather than reported as perfect. Document foreground fractions are diagnostics, not OCR accuracy. Median-filter PSNR is **30.12 dB**, compared with **17.77 dB** for the simulated noisy image; this is a one-image experiment.

## Run in Google Colab

1. Open https://colab.research.google.com/.
2. Select **File → Upload notebook** and upload `digital_image_processing_cases.ipynb`.
3. Select **Runtime → Run all**.
4. The notebook loads the official sample images automatically. No API key or Google Drive access is needed.
5. Generated files appear under `figures/`, `images/`, and `results/` in the runtime file browser. Download them before the temporary Colab runtime expires.

The notebook was tested locally from top to bottom with Python 3.9, NumPy 2.0.2, and scikit-image 0.24.0. It has not been independently run on the hosted Colab service.

## Run locally

```sh
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

Open the notebook with a Jupyter-compatible editor and select the virtual environment. To execute it without an editor:

```sh
python -c "import nbformat; from nbclient import NotebookClient; p='digital_image_processing_cases.ipynb'; n=nbformat.read(p,as_version=4); NotebookClient(n,timeout=180,kernel_name='python3').execute(); nbformat.write(n,p)"
```

`create_notebook.py` regenerates an **unexecuted** notebook, replacing its current outputs; normally you do not need to run it.

## Compile the report

Requires TeX Live with pdfLaTeX, BibTeX, and latexmk:

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=build main.tex
cp build/main.pdf main.pdf
```

Compilation passed with all citations and cross-references resolved. The remaining warnings are non-fatal underfull horizontal boxes in the keywords and long bibliography URLs. The report uses the official IEEE conference class, not a manually approximated two-column layout.

## GitHub repository

- Repository: https://github.com/MalpinPasquale/PCD_Assignment4
- Previous report PDF: https://github.com/MalpinPasquale/PCD_Assignment4/blob/main/main.pdf
- Optional notebook in Colab: https://colab.research.google.com/github/MalpinPasquale/PCD_Assignment4/blob/main/digital_image_processing_cases.ipynb

For future updates, review `git status` and `git diff`, commit the intended changes, and push to the existing `origin` remote. Do not repeat repository creation.

## Sources and attribution

See [`images/SOURCES.md`](images/SOURCES.md), the notebook's source section, and the report bibliography. Search-engine results were used to locate the authoritative collection, not treated as image ownership or licensing permission.
