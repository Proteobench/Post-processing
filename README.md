# Post-processing

Here we collect Jupyter notebooks, Quarto documents, and Marimo notebooks that investigate the [ProteoBench](https://proteobench.cubimed.rub.de/) data.

Examples include testing new and additional benchmarking metrics, parallel processing of uploaded data files, and manuscript-ready visualizations.

## Contents

### Submission Utilities

Tools for preparing and converting data before uploading to ProteoBench.

| Notebook | Description |
|---|---|
| [`submission/ProteoBench_input_conversion.ipynb`](submission/ProteoBench_input_conversion.ipynb) | Prepares ProteoBench inputs from software tool outputs where the required information is spread across more than one file. |
| [`utils/create_mapper.ipynb`](utils/create_mapper.ipynb) | Creates a protein description–to–gene name mapper CSV from FASTA files, used by the ProteoBench parsing layer. |

### Single-Submission Analysis

Notebooks for inspecting and visualizing results from an individual ProteoBench submission.

| Notebook | Description |
|---|---|
| [`analysis/single_submission/quant/lfq/ion/dda/logFCs_per_organism_plots.ipynb`](analysis/single_submission/quant/lfq/ion/dda/logFCs_per_organism_plots.ipynb) | Demonstrates how to create figures from ProteoBench intermediate files. Reproduces an intensity-vs-logFC plot (similar to Fig. 3d in the ion-quantification benchmark publication by Van Puyvelde et al., 2022). |

### Post-Analysis — DDA Ion Quantification

Cross-submission analyses for data-dependent acquisition (DDA) ion-level label-free quantification modules.

| Notebook / Document | Format | Description |
|---|---|---|
| [`analysis/post_analysis/quant/lfq/ion/dda/DDA_ion_quant_manuscript.ipynb`](analysis/post_analysis/quant/lfq/ion/dda/DDA_ion_quant_manuscript.ipynb) | Jupyter | Generates manuscript figures for the DDA ion quantification module, including upset plots and intensity boxplot comparisons across software tools. |
| [`analysis/post_analysis/quant/lfq/ion/dda/indepth_module_analysis.ipynb`](analysis/post_analysis/quant/lfq/ion/dda/indepth_module_analysis.ipynb) | Jupyter | In-depth performance benchmarking: downloads all public DDA submissions, re-runs the ProteoBench scoring pipeline, and measures load, conversion, and benchmarking times per tool. |
| [`analysis/post_analysis/quant/lfq/ion/dda/indepth.qmd`](analysis/post_analysis/quant/lfq/ion/dda/indepth.qmd) | Quarto | Quarto version of the in-depth module analysis above, suitable for rendering as a self-contained HTML report. |
| [`analysis/post_analysis/quant/lfq/ion/dda/scores_dissected.py`](analysis/post_analysis/quant/lfq/ion/dda/scores_dissected.py) | Marimo | Interactive accuracy-vs-precision analysis for DDA quantification: loads benchmark results from GitHub and produces per-species scatter and box plots. |
| [`analysis/post_analysis/quant/lfq/ion/dda/plot_runs_sage.ipynb`](analysis/post_analysis/quant/lfq/ion/dda/plot_runs_sage.ipynb) | Jupyter | Downloads Sage search results from Figshare and plots metric performance across multiple Sage parameter configurations. |

### Post-Analysis — DIA Ion Quantification

Cross-submission analyses for data-independent acquisition (DIA) ion-level label-free quantification modules.

| Notebook | Format | Description |
|---|---|---|
| [`analysis/post_analysis/quant/lfq/ion/dia/astral_diaPasef/Astral_diaPASEF_manuscript.ipynb`](analysis/post_analysis/quant/lfq/ion/dia/astral_diaPasef/Astral_diaPASEF_manuscript.ipynb) | Jupyter | Manuscript figures for the Astral and diaPASEF DIA modules: downloads submissions from GitHub, re-scores them, and generates upset plots and metric scatter plots. |

### Multi-Module Overview

| Notebook | Format | Description |
|---|---|---|
| [`analysis/post_analysis/quant/lfq/ion/benchmark_analysis.py`](analysis/post_analysis/quant/lfq/ion/benchmark_analysis.py) | Marimo | Interactive benchmark dashboard supporting multiple DDA and DIA modules. Loads results from GitHub and renders per-species accuracy-vs-precision scatter plots with a configurable module selector. |
| [`analysis/post_analysis/quant/lfq/ion/index.py`](analysis/post_analysis/quant/lfq/ion/index.py) | Marimo | Index page listing all available ProteoBench benchmark analysis reports with submission counts per module and links to the individual HTML reports. |

### Exploratory Analysis

| Notebook | Description |
|---|---|
| [`analysis/methionine_excision_analysis.ipynb`](analysis/methionine_excision_analysis.ipynb) | Analyses all publicly submitted ProteoBench datasets to determine which software tools apply N-terminal methionine excision (NME) and whether there is a systematic difference between tools ([related issue #504](https://github.com/Proteobench/ProteoBench/issues/504)). |

## Contributing

Contributions are very welcome! You can contribute:

- **Jupyter notebooks** (`.ipynb`) — the classic format for interactive analysis.
- **Marimo notebooks** (`.py`) — reactive Python notebooks that are version-control-friendly and can be run as scripts or apps.
- **Quarto documents** (`.qmd`) — literate programming documents that render to HTML, PDF, or other formats.

If you have an analysis, visualization, or utility script that builds on ProteoBench data, feel free to open a pull request. Please place your contribution in the most appropriate subdirectory (e.g. `analysis/`, `submission/`, `utils/`) and add a short description to this README.
