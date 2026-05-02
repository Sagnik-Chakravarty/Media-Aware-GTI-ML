# Outputs

This directory is reserved for generated output files from the media-aware GTI workflow.

Recommended subdirectories:

```text
outputs/
  tables/
  figures/
```

Current root-level outputs include:

- `gti_ranking.csv`: country-level baseline vs. ML-predicted ranking comparison.
- `gti_score_calculated.csv`: calculated country-level GTI-like scores and model outputs.

Future cleanup can move these root-level outputs into `outputs/tables/` while preserving links in the README.
