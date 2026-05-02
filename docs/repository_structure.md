# Repository Structure

This repository keeps the original project files while adding clearer documentation for portfolio and reviewer use.

```text
.
├── README.md
├── MachineLearning.qmd
├── Scrapping/
│   └── Webscrapping.py
├── Data/
│   └── reuters_combined.csv
├── gti_ranking.csv
├── gti_score_calculated.csv
└── docs/
    ├── project_overview.md
    ├── methods_summary.md
    └── repository_structure.md
```

## Main Analysis Files

- `MachineLearning.qmd`: Main R/Quarto workflow for text preprocessing, framing classification, GTD aggregation, GTI-like score construction, random forest modeling, residual analysis, maps, and interpretability diagnostics.
- `Scrapping/Webscrapping.py`: Python/Playwright scraping workflow for collecting article metadata from news sources.

## Data and Outputs

- `Data/reuters_combined.csv`: Combined Reuters article metadata used in the media-framing workflow.
- `gti_ranking.csv`: Country-level ranking comparison output.
- `gti_score_calculated.csv`: Country-level GTI-like calculated score and model output dataset.

## Documentation

- `docs/project_overview.md`: Research motivation, questions, data sources, and main outputs.
- `docs/methods_summary.md`: Summary of data collection, preprocessing, modeling, and interpretation workflow.
- `docs/repository_structure.md`: This file.

## Suggested Future Cleanup

For a production-level version, the next step would be to move files into dedicated directories such as:

```text
analysis/
  media_aware_gti_model.qmd
scraping/
  news_scraper.py
data/
  raw/
  processed/
outputs/
  tables/
  figures/
docs/
```

The current repository preserves the original paths to avoid breaking existing project links.
