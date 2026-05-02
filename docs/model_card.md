# Model Card: Media-Aware GTI Prototype

## Model Purpose

This model is an exploratory research prototype that combines structured terrorism event indicators with media-framing variables to study country-level terrorism severity rankings.

It is intended for methodological exploration, policy-measurement critique, and interpretability analysis. It should not be used as an official terrorism-risk score.

## Inputs

### Structured Event Inputs

- country-level incident counts,
- fatalities,
- injuries,
- hostages/kidnappings.

### Media-Framing Inputs

- article-level framing labels,
- country-level framing proportions,
- terrorism-framing ratio,
- state-violence-framing ratio,
- total article count by country.

## Outputs

- baseline GTI-like score,
- ML-predicted GTI-like score,
- country-level rank difference,
- residuals,
- feature importance,
- local explanations for selected countries.

## Modeling Approach

The workflow uses:

1. decision-tree classification for article-level media framing,
2. country-level aggregation of event and framing variables,
3. random forest regression for GTI-like score prediction,
4. interpretability diagnostics using feature importance, residuals, maps, and DALEX explanations.

## Intended Use

- Research portfolio demonstration.
- Exploratory policy-measurement analysis.
- Example of interpretable ML applied to public-policy rankings.
- Demonstration of combining structured administrative/event data with unstructured media data.

## Limitations

- The framing classifier depends on a limited hand-labeled subset.
- News-source coverage may be selective and uneven across countries.
- Country matching from article text can introduce classification error.
- The GTI-like score is a simplified reconstruction, not the official GTI methodology.
- Media framing is not a ground-truth measure of terrorism severity.
- Results should be interpreted as exploratory and hypothesis-generating.

## Ethical Considerations

Terrorism labels and country-level risk rankings can affect public perception and policy debate. This project therefore emphasizes interpretability, documentation, and caution in interpretation. The goal is not to assign definitive country labels, but to examine how measurement choices and media framing may shape ranking outputs.
