# Efficient-bioMoR

Project page for **bioMoR: Biology-Guided Mixture-of-Recursions for Effective Genomic Learning**.

> **Status:** manuscript under review — not yet accepted or published.

Static site built on the [Academic Project Page Template](https://github.com/eliahuhorwitz/Academic-project-page-template)
(adopted from [Nerfies](https://nerfies.github.io)), matching the styling of the
[SAGE](https://sage-dataset.github.io/) project page.

## Layout

```
index.html                 # the whole page
static/css/                # bulma + carousel/slider + fontawesome + index.css
static/js/                 # bulma-carousel, bulma-slider, fontawesome, index.js
static/images/             # figures rasterized from the paper's PDFs
static/paper/paper.pdf     # the manuscript
.github/workflows/static.yml  # deploys the repo root to GitHub Pages on push to main
```

## Figures

Every figure from the main paper is on the page, rasterized from `figs/*.pdf` with
`pdftoppm -r 600 -png -singlefile` (600 dpi). Supplementary figures are deliberately not shown:

| Page image | Source PDF | Paper location |
| --- | --- | --- |
| `overview.png` / `teaser.png` | `overview.pdf` | Fig. 1 — system overview |
| `sota_compare.png` | `sota_compare.pdf` | Fig. 4 — external baselines |
| `survival_cindex.png` | `survival_cindex.pdf` | Fig. 2 — TCGA survival |
| `ablation_bar.png` | `ablation_bar.pdf` | Fig. 5 — injection-site ablation |
| `t_cell_efficiency.png` | `t_cell_efficiency.pdf` | Fig. 6 — training/compute efficiency |
| `umap_viz.png` | `umap_viz_old.pdf` | Fig. 3 — frozen-embedding linear probe |
| `case_study.png` | `case_study.pdf` | Fig. 7 — biological case study |

To refresh a figure after the paper changes:

```bash
pdftoppm -r 600 -png -singlefile /path/to/figs/<name>.pdf static/images/<name>
```

## Preview locally

```bash
python3 -m http.server 8000   # then open http://localhost:8000
```

## TODO before the page goes public

- [ ] Replace the `arXiv (soon)` button's `href="#"` with the arXiv abs URL.
- [ ] Point the `Code` button at the actual code repository (currently the org page).
- [ ] Update the BibTeX from `@unpublished{howlader2026biomor, ...}` to the published reference once
      the paper is accepted, and swap the `Under Review` tag for the venue.
