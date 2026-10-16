# Repeated Measures Analysis

This repository contains statistical analyses and scripts for analyzing datasets with repeated measures including longitudinal and paired data. The primary focus is on modeling within-subject correlations and evaluating changes over time using linear mixed-effects models.

The folder includes computations and models for two distinct datasets: **hp** (Heart Period) and **pss** (Perceived Stress Score).

---

## Datasets Description

### 1. Heart Period Dataset (`hp`)
This dataset contains measurements of the 'heart period' to study differences in cardiovascular metrics depending on physical status and time of day.

- $\text{group}$: Ether the person is physically active or passive. 

- $\text{day}$: Average time in milliseconds between two consecutive heartbeats during the day

- $\text{night}$: Average time in milliseconds between two consecutive heartbeats during the night

### 2. Perceived Stress Score Dataset (`pss`)
This dataset originates from a study by Willert et al. (2009). It includes 102 stressed participants randomized into either a three-month stress management treatment or a waitlist control group. Measurements were recorded at three specific milestones: baseline, 3 months, and 6 months post-randomization.

**$\text{id}$:** The patients ID-number

**$\text{maaling}$:** Time the measurement for made: 

  - 1: Baseline (before the randomization) 
  
  - 2: 3 months before the randomization
  
  - 3: 6 months before the randomization
 
**$\text{gruppe}$:** Indicates which experimental group the participant was randomized to. The variable has two levels:

  - Intervention: The group that immediately started three months of stress management treatment.
  
  - Venteliste (Waitlist): The control group that waited for three months before receiving the same treatment.
  
**$\text{pss}$:** Stands for Perceived Stress Score. It is s a continuous/numerical variable on a scale from 0 to 40, where a higher score indicates a higher level of perceived stress. The value NA (Not Available) indicates missing data for that specific measurement.

---

## Statistical Methodology
The analyses in this repository utilize **Linear Mixed-Effects Models (LMM)** via the `lme4` and `emmeans` packages in R. This approach accounts for the random variations between individual subjects (`id`) while examining the fixed main effects and interactions of experimental groupings and time points.

Outputs include:
* Estimated Marginal Means (EM Means) stratified by groups.
* Pairwise comparisons (Simple Effects / Mean Differences) evaluating the changes across time conditions.