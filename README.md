# Machine Learning–Driven Discovery of Stable Heusler Alloys

This project investigates supervised and generative machine learning approaches for predicting thermodynamic stability in Heusler compounds. The work combines compositional feature engineering, graph neural networks, and generative adversarial modeling to identify stable intermetallic materials.

---

## 1. Problem Statement

Heusler alloys (X₂YZ compositions) are ternary intermetallic compounds with applications in spintronics, magnetic materials, and thermoelectric systems. Determining thermodynamic stability traditionally requires density functional theory (DFT) calculations, which are computationally expensive.

The objective of this project is to:

- Predict stability from compositional and structural features
- Regress formation energy values
- Generate candidate stable compositions using generative models

---

## 2. Dataset

### Source

Data was curated from publicly available materials databases (e.g., Materials Project / OQMD-type repositories), containing computed DFT formation energies and stability labels for Heusler compounds.

### File Format

Data files are stored in structured CSV format:

- `composition.csv`
- `formation_energy.csv`
- `stability_labels.csv`

Each row corresponds to a unique compound with:

- Elemental composition (X, Y, Z)
- Stoichiometric ratios
- Formation energy (eV/atom)
- Stability classification (stable / unstable)
- Derived compositional descriptors

### Preprocessing

- Removal of incomplete entries
- Normalization of continuous descriptors
- Encoding of compositional features
- Train/test split with stratification for classification tasks

---

## 3. Methodology

### 3.1 Feature-Based Supervised Learning

**Model:** XGBoost Classifier  
**Task:** Binary stability prediction  

- Compositional descriptors engineered from elemental properties (atomic radius, electronegativity, valence electrons, etc.)
- Gradient boosted decision trees
- Hyperparameter tuning via cross-validation
- Model interpretability using SHAP values

**Evaluation Metrics:**
- Accuracy
- Precision / Recall
- ROC-AUC

Results demonstrated strong classification performance on held-out test data, with high precision in identifying stable compounds.

---

### 3.2 Graph Neural Network (CGCNN)

**Model:** Crystal Graph Convolutional Neural Network  
**Task:** Formation energy regression  

- Crystal structures represented as graphs (atoms as nodes, bonds as edges)
- Convolutional layers aggregate local atomic environments
- Fully connected layers map graph embeddings to formation energy

**Evaluation Metrics:**
- Mean Absolute Error (MAE)
- R² score

The CGCNN model achieved strong predictive performance for formation energy regression, capturing structural dependencies beyond compositional features.

---

### 3.3 Generative Modeling (Conditional WGAN-GP)

**Model:** Conditional Wasserstein GAN with Gradient Penalty  
**Task:** Generate candidate stable compositions  

- Generator conditioned on stability labels
- Gradient penalty for training stability
- Evaluation via distribution alignment with real stable compounds

Generated samples were analyzed against learned compositional distributions to assess plausibility and stability likelihood.

---

## 4. Results Summary

- High classification accuracy for stability prediction using XGBoost
- Strong R² performance for formation energy regression using CGCNN
- Conditional GAN capable of generating compositionally plausible candidate compounds
- SHAP analysis revealed dominant compositional features influencing stability

---

## 5. Repository Structure

- `notebooks/` – exploratory experiments
- `data/` – dataset references
- `reports/` – project report


---

Author: Moulik Kumar
