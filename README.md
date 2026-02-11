# Machine Learning–Driven Discovery of Stable Heusler Alloys

This project explores supervised and generative machine learning approaches for predicting thermodynamic stability in Heusler compounds.

## Overview

Heusler alloys are intermetallic compounds with applications in spintronics, magnetism, and thermoelectric materials. The goal of this project is to:

- Predict formation energy and stability
- Identify compositional patterns associated with stable structures
- Generate candidate compounds using generative models

## Methodology

### 1. Feature-Based Models
- Compositional feature engineering
- XGBoost classification for stability prediction
- SHAP-based interpretability analysis

### 2. Graph Neural Networks
- Crystal Graph Convolutional Neural Networks (CGCNN)
- Regression on formation energy
- R² evaluation on test sets

### 3. Generative Modeling
- Conditional WGAN-GP
- Stability-conditioned composition generation
- Evaluation of generated candidates against learned distributions

## Results

- High classification accuracy for stability prediction
- Strong R² performance for energy regression
- Successful generation of plausible stable candidate compositions

## Repository Structure

- `src/` – model implementations
- `notebooks/` – exploratory experiments
- `data/` – dataset references
- `results/` – model outputs
- `figures/` – visualizations

## Requirements

See `requirements.txt`

---

Author: Moulik Kumar
