# Methods Summary

## 1. News Collection

The project uses Playwright-based scraping scripts to collect terrorism-related article metadata from international news outlets. The keyword list includes terms such as terrorism, terrorist attack, insurgency, political violence, state crackdown, counter-terrorism operations, and related phrases.

Collected article fields include:

- headline,
- snippet,
- date,
- link,
- keyword,
- source.

## 2. Text Preprocessing

News headline and snippet fields are combined into a single text field. Text is then cleaned using standard NLP preprocessing steps:

- lowercasing,
- punctuation removal,
- number removal,
- stopword removal,
- whitespace normalization,
- stemming.

## 3. Framing Classification

A labeled subset of news articles is used to train a decision-tree classifier for media framing. The framing categories include:

- Terrorism,
- State Violence,
- Insurgency,
- Freedom Fighter,
- Neutral.

The model uses TF-IDF features derived from cleaned article text. Training uses an 80/20 train-test split and cross-validation through `caret`.

## 4. Country-Level Framing Aggregation

Predicted article-level framing labels are aggregated to the country level. For each country, the workflow computes counts and proportions of framing categories, such as terrorism-framing ratio and state-violence-framing ratio.

## 5. GTI-Like Score Construction

Structured GTD event records are aggregated by country using:

- incident count,
- fatalities,
- injuries,
- hostages/kidnappings.

These indicators are normalized to a 0–10 scale and combined into a baseline GTI-like score.

## 6. ML-Based GTI Modeling

A random forest regression model is trained to predict GTI-like scores from event indicators and media-framing features. The workflow produces:

- predicted country scores,
- feature importance,
- residual diagnostics,
- rank comparisons,
- maps and visualizations.

## 7. Interpretability and Diagnostics

The project uses several interpretability and diagnostic tools:

- feature importance from the random forest model,
- residual plots,
- country-level rank differences,
- local explanations using DALEX,
- classification diagnostics for framing labels.

## Methodological Caution

This project is exploratory and should be interpreted as a research prototype. Media-framing variables are not treated as ground truth measures of terrorism severity. Instead, they are used to examine how narrative context may affect or complicate country-level policy rankings.
