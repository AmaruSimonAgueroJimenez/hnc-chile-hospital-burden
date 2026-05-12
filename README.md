# hnc-chile-hospital-burden

Hands-on application of methods from a Social Complexity Sciences PhD — spatial epidemiology, hierarchical prognostic models, and comorbidity networks — applied to head and neck cancer (HNC) hospitalizations in Chile, 2010–2024.

**Live site (GitHub Pages):** [amarusimonaguerojimenez.github.io/hnc-chile-hospital-burden](https://amarusimonaguerojimenez.github.io/hnc-chile-hospital-burden/)

## Overview

The project uses public hospital discharge data (GRD — *Grupos Relacionados por el Diagnóstico*) from the Chilean Ministry of Health, combined with national census projections and administrative shapefiles, to characterize the burden of head and neck malignant neoplasms (ICD-10 C00–C14, C30–C32) across three complementary perspectives:

1. **Spatial epidemiology** — age-standardized hospitalization rates and spatial clustering, 2010–2024.
2. **Prognosis** — hierarchical models of in-hospital mortality and length of stay, 2019–2024.
3. **Comorbidity networks** — network analysis of co-occurring diagnoses in HNC hospitalizations, 2019–2024.

## Reports

All reports are rendered from Quarto (`.qmd`) sources and published on GitHub Pages.

| # | Report | Source |
|---|--------|--------|
| 1 | [Age-standardized trends &amp; spatial clustering](https://amarusimonaguerojimenez.github.io/hnc-chile-hospital-burden/neoplasias_cabeza_cuello_parte1.html) | `docs/neoplasias_cabeza_cuello_parte1.qmd` |
| 2 | [In-hospital mortality &amp; length of stay](https://amarusimonaguerojimenez.github.io/hnc-chile-hospital-burden/neoplasias_cabeza_cuello_parte2.html) | `docs/neoplasias_cabeza_cuello_parte2.qmd` |
| 3 | [Comorbidity network analysis](https://amarusimonaguerojimenez.github.io/hnc-chile-hospital-burden/neoplasias_cabeza_cuello_redes.html) | `docs/neoplasias_cabeza_cuello_redes.qmd` |
| · | [Network analysis in health sciences (supplementary, ES)](https://amarusimonaguerojimenez.github.io/hnc-chile-hospital-burden/net%28esp%29.html) | `docs/net(esp).qmd` |

## Materials

- [Unified project abstract (DOCX)](https://amarusimonaguerojimenez.github.io/hnc-chile-hospital-burden/abstract_unificado_cabeza_cuello.docx)
- [15-minute presentation (PPTX)](https://amarusimonaguerojimenez.github.io/hnc-chile-hospital-burden/Presentacion_CCyC_15min.pptx)

## Repository layout

```
hnc-chile-hospital-burden/
├── docs/                     # Published HTML site (GitHub Pages source)
│   ├── index.html            # Landing page
│   ├── *.qmd                 # Quarto sources of the reports
│   ├── *.html                # Rendered reports
│   ├── *.bib                 # Bibliographies
│   ├── net(esp)_files/       # Quarto asset folder (libs/)
│   ├── abstract_unificado_cabeza_cuello.docx
│   └── Presentacion_CCyC_15min.pptx
├── data/                     # Raw inputs (not versioned — see .gitignore)
├── outputs/ , output_files/  # Generated artifacts (not versioned)
└── README.md
```

The `data/`, `outputs/`, and `output_files/` directories are deliberately excluded from version control because they are large (≈ 7 GB combined) and regenerable from the raw GRD CSVs.

## Data sources

- **GRD (hospital discharges):** Chilean Ministry of Health public release, 2019–2024 (CSV) and historical extraction 2010–2018.
- **Census projections:** national age × sex × year projections (Parquet).
- **Geography:** administrative shapefiles (commune / region level).
- **Code dictionary:** ICD-10 and GRD groupings used to build the cohort (kept locally under `data/`).

## Reproducing the analyses

1. Place the raw GRD CSVs and supporting files under `data/` (paths are referenced inside each `.qmd`).
2. Render any report with Quarto:
   ```bash
   quarto render docs/neoplasias_cabeza_cuello_parte1.qmd
   ```
3. The rendered HTML is written next to its source inside `docs/` and is what GitHub Pages serves.

## Publishing

GitHub Pages is configured to serve from `main` → `/docs`. A `.nojekyll` file is included so that Quarto's `*_files/` asset folders (Bootstrap, popper, tippy, etc.) are served as-is.

## Citation

If you use this material, please cite as:

> Agüero-Jiménez, A. S. *Hospital burden of head and neck cancer in Chile, 2010–2024.* GitHub repository, 2026. https://github.com/AmaruSimonAgueroJimenez/hnc-chile-hospital-burden

## License

Code is released under the MIT License. Reports and figures are released under CC BY 4.0 unless otherwise noted.

## Contact

Amaru Simón Agüero-Jiménez — `amaruaguero2004@ug.uchile.cl`
