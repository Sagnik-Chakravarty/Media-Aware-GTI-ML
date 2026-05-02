# Media-Aware Global Terrorism Index (GTI-ML)

This repository contains an interpretable machine-learning project that combines structured terrorism event records with media-framing indicators to examine country-level terrorism severity rankings. The project uses data from the Global Terrorism Database (GTD), international news coverage, text classification, and random forest modeling to create a media-aware GTI-style analysis.

## Repository Description

Interpretable ML project combining Global Terrorism Database event records with media-framing signals from international news to analyze country-level terrorism severity, ranking differences, residuals, and feature importance.

## Project Motivation

Policy rankings such as the Global Terrorism Index summarize complex patterns of political violence into country-level scores. These rankings are useful, but they may hide important measurement choices. This project examines how country-level terrorism rankings can change when structured event indicators are combined with media-framing variables.

The goal is not to replace the official GTI. Instead, the project asks whether a media-aware modeling workflow can help identify cases where event severity and narrative framing diverge.

## Research Questions

1. Can structured GTD event indicators be combined with media-framing features in an interpretable ML workflow?
2. Which event and framing variables are most influential in predicted country-level terrorism severity?
3. Which countries show the largest differences between baseline GTI-like scores and ML-predicted rankings?
4. Can residual analysis and feature attribution help evaluate potential framing effects or measurement gaps?

## Data Sources

- **Global Terrorism Database (GTD):** incident-level terrorism event records.
- **International news data:** article metadata and snippets from sources including Reuters, Al Jazeera, and The Washington Post.
- **Hand-labeled framing data:** labeled news examples used to train a framing classifier.

## Methods

The workflow includes:

- Playwright-based news scraping,
- text cleaning and preprocessing,
- TF-IDF feature construction,
- decision-tree framing classification,
- country-level aggregation of framing categories,
- GTD-based event aggregation,
- GTI-like score construction,
- random forest regression,
- country-level rank comparison,
- residual analysis,
- feature importance,
- local interpretability using DALEX,
- map-based visualization.

## Framing Categories

The article-level classifier uses five framing labels:

- `Terrorism`
- `State Violence`
- `Insurgency`
- `Freedom Fighter`
- `Neutral`

## Repository Structure

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
├── analysis/
│   └── README.md
├── outputs/
│   └── README.md
└── docs/
    ├── project_overview.md
    ├── methods_summary.md
    ├── model_card.md
    └── repository_structure.md
```

## Main Files

### Analysis

- `MachineLearning.qmd`: Main R/Quarto analysis workflow. Includes text preprocessing, framing classification, GTD aggregation, GTI-like score construction, random forest modeling, residual analysis, maps, and interpretability diagnostics.

### Scraping

- `Scrapping/Webscrapping.py`: Python/Playwright scraping workflow for collecting terrorism-related article metadata from news sources.

### Data and Outputs

- `Data/reuters_combined.csv`: Reuters article metadata used in the media-framing workflow.
- `gti_ranking.csv`: Country-level ranking comparison between baseline and ML-predicted scores.
- `gti_score_calculated.csv`: Country-level calculated GTI-like scores and model outputs.

### Documentation

- `docs/project_overview.md`: Research motivation, questions, data sources, and outputs.
- `docs/methods_summary.md`: Summary of scraping, preprocessing, modeling, and interpretability workflow.
- `docs/model_card.md`: Intended use, limitations, inputs, outputs, and ethical considerations.
- `docs/repository_structure.md`: Explanation of the repository layout.

## Key Outputs

- Country-level GTI-like scores.
- ML-predicted country-level terrorism severity scores.
- Country rank differences between baseline and model-predicted outputs.
- Feature-importance plots identifying influential event and framing variables.
- Residual diagnostics to identify countries where model predictions diverge from baseline scores.
- Global map visualizations of predicted scores and score differences.

## Skills Demonstrated

- Public-policy measurement and index critique
- Web scraping with Python and Playwright
- Text preprocessing and TF-IDF modeling
- Supervised text classification
- Random forest regression
- Feature importance and interpretability
- Residual analysis
- Country-level aggregation and ranking comparison
- R/Quarto reproducible analysis
- Data visualization and policy-facing documentation

## Limitations

This is an exploratory research prototype. The GTI-like score is a simplified reconstruction and should not be interpreted as the official GTI methodology. Media-framing variables are not ground-truth measures of terrorism severity. News-source coverage can be uneven across countries, and country matching from article text can introduce classification error.

## How to Use

1. Open `MachineLearning.qmd` in RStudio or another Quarto-compatible environment.
2. Install required R packages, including `tidyverse`, `caret`, `text2vec`, `rpart`, `randomForest`, `ggplot2`, `sf`, `rnaturalearth`, and `DALEX`.
3. Run the workflow to reproduce the framing classifier, GTI-like score construction, model fitting, ranking comparison, and diagnostics.
4. Use the documentation in `docs/` to understand the research design and limitations.

## Author

**Sagnik Chakravarty**  
M.S. Survey and Data Science, University of Maryland, College Park  
Portfolio: https://sagnik-chakravarty.github.io/  
GitHub: https://github.com/Sagnik-Chakravarty
