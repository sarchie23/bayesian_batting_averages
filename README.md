# Project Overview

Over the past two decades, Major League Baseball (MLB) has experienced a noticeable decline in batting averages. In 2000, the league batting average was approximately .276, with 81 players hitting above .300. By 2023, the league average had dropped to .251 and only 16 players surpassed the .300 mark. 

This project investigates the factors contributing to this decline using Statcast data and a Bayesian multilevel modeling framework. The goal of the analysis is to determine whether league-wide changes (such as defensive shifts or pitching strategy) or player-level effects (such as batter and pitcher skill) better explain the observed trend. To address this question, we built a Bayesian multilevel logistic regression model predicting the probability that a plate appearance results in a hit.

# Data
Data were obtained from MLB Statcast using the baseballr R package. Statcast provides pitch-level and plate-appearance-level information for MLB games from 2015-2024 seasons.

# Model
We use a Bayesian multilevel logistic regression model. The outcome variable is whether a plate appearance resulted in a hit.

The model includes pitch-level predictors such as:
- pitch velocity
- pitch movement
- pitch location
- batter age

The model includes random intercepts for:
- batter
- pitcher
- team
- year

The model was implemented in R using the brms package, which compiles Bayesian models into Stan code for sampling.

# Findings
- Batter skill is the largest driver of variation in hit probability.
- Pitcher effects also contribute meaningfully.
- League-wide effects such as shifts or strategic changes appear less influential than expected.

These results suggest that declining batting averages may be more closely tied to the evolving balance of pitcher and batter talent than to systemic rule or strategy changes.

The full report can be found [here](https://docs.google.com/document/d/17c2o7EFKines5UShSIxJJPq4FQIeX7wbIDnGrmPT4Ss/edit?tab=t.0#heading=h.3hhpy0phhdyg).

# Repo structure
- eda_viz contains some visualizations related to changes in batting average over time.
- model contains the data cleaning and model generation steps.
