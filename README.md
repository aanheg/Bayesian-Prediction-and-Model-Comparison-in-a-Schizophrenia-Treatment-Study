# Bayesian Prediction and Model Comparison in a Schizophrenia Treatment Study

A Bayesian analysis of a randomized clinical trial comparing an antipsychotic drug versus placebo in patients with schizophrenia. Symptom severity (IMPS79, scale 1–7) was measured repeatedly from baseline through Week 6.

## Overview

This project applies Bayesian statistical methods across four aims:

1. **Baseline comparability** — Are the drug and placebo groups balanced at Week 0?
2. **Longitudinal trajectories** — How does symptom severity evolve over time in each group, accounting for between-patient variability via random intercepts?
3. **Posterior prediction** — For a new patient, what is the probability of achieving a clinically meaningful outcome (IMPS79 ≤ 3) at Week 6 under each treatment?
4. **Model comparison** — Which regression model for change from baseline to Week 6 is best supported by the data?

## Key Results

| | Estimate |
|---|---|
| Baseline mean difference (Drug − Placebo) | 0.02, 95% CrI [−0.27, 0.30] |
| Placebo improvement per week | −0.15 IMPS79 points |
| Drug improvement per week | −0.37 IMPS79 points (~2.5× faster) |
| P(IMPS79 ≤ 3 at Week 6 \| Placebo) | ~17% |
| P(IMPS79 ≤ 3 at Week 6 \| Drug) | ~55% |
| Best model (Bayesian comparison) | Treatment + baseline severity (posterior prob ≈ 1.00) |

## Methods

- Two-group normal model with conjugate NIG priors for baseline comparison
- Hierarchical linear regression with patient-specific random intercepts
- Custom Gibbs sampler (20,000 iterations, 5,000 burn-in) with trace plot diagnostics
- Closed-form marginal likelihoods for Bayesian model comparison across 3 nested models

## Files

| File | Description |
|---|---|
| `Bayesian_Schizophrenia_Final_Project.Rmd` | Full analysis with code |
| `Bayesian-Schizophrenia-Final-Project.pdf` | Rendered report with results and plots |
| `Proposal-Schizophrenia.pdf` | Project proposal outlining research questions and planned models |

## Data

Publicly available schizophrenia clinical trial dataset:  
https://hbiostat.org/data/repo/schizophrenia  
(1,603 observations; patients measured at Weeks 0, 1, 2, 3, 4, 5, 6)

## Tools

- **Language:** R
- **Key packages:** `ggplot2`, `dplyr`, `tidyr`
- **MCMC:** Custom Gibbs sampler (base R)

## Context

Graduate-level Bayesian Statistics course project — Indiana University Bloomington, Fall 2025.
