# state_of_open_funding_data_processing
Data processing pipeline for the grant funding dataset underpinning IOI's State of Open Infrastructure (SoOI) 2026 report.

Full methodology, including pipeline steps, classifier design, and evaluation stats, is documented in the data deposit on Zenodo: [10.5281/zenodo.21401121](https://doi.org/10.5281/zenodo.21401121). This repo holds the code referenced there.

## Pipeline overview

Notebooks run in sequence, each consuming the previous step's output:

1. `01_combine_sources.ipynb`
2. `02_deduplicate.ipynb`
3. `03_grant_fp_classifier_inference.ipynb`
4. `04_grant_categorisation_classifier_inference.ipynb`
5. `05_enrich.ipynb`

**Output:** `enriched.csv`

## Supporting folders

- `false_positive_classifier/` — classifier scripts and supporting files for step 3
- `award type classifier/` — classifier scripts and supporting files for step 4
- `reference/` — frozen reference data (e.g. ECB exchange rate history) used across the pipeline

## Models used

- **False-positive classification (step 3):** Claude Sonnet
- **Categorisation (step 4):** Claude Haiku

See the Zenodo methods documentation for model selection rationale and evaluation figures.

## License

MIT — see `LICENSE`.
