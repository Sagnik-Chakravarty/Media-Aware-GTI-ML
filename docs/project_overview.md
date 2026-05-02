# Project Overview

## Media-Aware Global Terrorism Index (GTI-ML)

This project develops an interpretable machine-learning extension of the Global Terrorism Index (GTI) by combining structured terrorism event data with media-framing indicators. The goal is not to replace official GTI-style measures, but to examine how country-level terrorism severity rankings may change when media narratives and framing categories are incorporated alongside incident-based indicators.

## Research Motivation

Policy rankings such as the Global Terrorism Index summarize complex political violence patterns into country-level scores. These rankings are useful because they simplify large event datasets, but they can also obscure how violence is interpreted, framed, and communicated across media systems.

This project asks whether a media-aware model can reveal differences between event-based terrorism severity and the way terrorism is framed in international news coverage.

## Research Questions

1. Can structured event indicators from the Global Terrorism Database be combined with media-framing variables to produce an interpretable GTI-like model?
2. Which event and framing variables contribute most strongly to country-level predicted terrorism severity?
3. Which countries show the largest rank differences between baseline GTI-like scores and ML-predicted scores?
4. Can residuals, feature importance, and local explanations help identify cases where media framing changes the interpretation of terrorism severity?

## Main Data Sources

- **Global Terrorism Database (GTD):** structured terrorism incident records, including country, fatalities, injuries, incidents, and hostage/kidnapping indicators.
- **International news data:** article-level headline/snippet data collected from media sources such as Reuters, Al Jazeera, and The Washington Post.
- **Hand-labeled framing data:** a labeled subset of news articles used to train a framing classifier.

## Main Outputs

- Framing classifier for terrorism-related news categories.
- GTI-like country scores based on structured event indicators.
- Random forest model incorporating event and framing features.
- Country-level rank comparison between baseline and ML-predicted scores.
- Residual analysis and feature-importance diagnostics.
- Map and figure outputs for visual interpretation.
