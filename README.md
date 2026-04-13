# Stream-Based Active Learning for Wood Age Prediction using FTIR Spectroscopy

This repository contains the code, notebooks and computational environment used in the Master's thesis:

**"Active Learning Strategies for Molecular Age Prediction: A Comparative Study of Random Forest and Gradient Boosting"**

---

## Project Overview

The aim of this thesis is to investigate the application of **Active Learning (AL)** strategies for regression tasks in the context of **spectroscopic wood dating**.

Specifically, the work focuses on:

- Predicting wood age from **FTIR spectral data** of *Pinus sylvestris*
- Comparing **supervised learning models**:
  - Random Forest (RF)
  - Gradient Boosting (GB / XGBoost)
- Evaluating **Active Learning strategies**:
  - Query-by-Committee (QBC)
  - Thresholding / IDEAL (exploration-based)
- Implementing a **Stream-Based Active Learning (SBS)** framework
- Assessing **label efficiency vs. predictive performance (RMSE)**

The dataset consists of spectroscopic measurements from wood samples originating from **Austria, Finland, Norway, and Poland**, covering different environmental conditions and preservation states.

---

## Reproducibility and Environment Setup

This project was developed using a **conda environment** to ensure full reproducibility.

To recreate the environment, run:

```bash
conda create --name <env_name> --file environment_list.txt
```

---

## Dependencies

The main libraries and frameworks used in this project include:

- **scikit-learn**  
  Machine learning framework used for regression models (e.g., Random Forest), preprocessing, and evaluation.

- **xgboost**  
  Gradient Boosting framework optimized for structured data and high predictive performance.

- **modAL**  
  Modular active learning framework used to implement Query-by-Committee (QBC).

- **numpy / pandas**  
  Core libraries for data handling, transformation, and numerical computations.

- **matplotlib / seaborn**  
  Visualization libraries used for plotting results and learning curves.

- **scipy**  
  Scientific computing and signal processing utilities.

---

## Repository Structure

├── notebooks/
│   ├── 01_model_development/   # Model training, optimization, and validation
│   ├── 02_active_learning/     # Stream-based active learning experiments (QBC, IDEAL)
├── data/                       # Input data (spectral datasets, metadata)
├── environment_list.txt        # Conda environment specification for reproducibility
└── README.md                  # Project documentation

---

## 📊 Notebook Structure

The workflow is organized into two main components:

### 🔹 Part 1: Model Development and Validation

These notebooks focus on building and validating regression models on spectral data:

- `XXX.ipynb`

#### Core Steps:
- Data loading and preprocessing  
- Train/test split  
- Feature scaling and transformation  
- Hyperparameter optimization  
- Model validation on test data  
- Permutation feature importance analysis  

---

### 🔹 Part 2: Stream-Based Active Learning

This notebook implements and evaluates active learning strategies:

- `XXX.ipynb`

#### Core Steps:
- Implementation of stream-based data processing  
- Random sampling baseline  
- Query-by-Committee (QBC)  
- Thresholding / IDEAL strategy  
- Comparison of query strategies  
- Evaluation of label efficiency vs. prediction accuracy  
- Analysis of selection behavior over time  

All experiments are conducted using both:

- **Random Forest (RF)**  
- **Gradient Boosting (GB / XGBoost)**  

---

## Methodological Workflow

The overall pipeline follows this structure:

1. Data acquisition and preprocessing  
2. Model training and validation  
3. Initialization with a seed set  
4. Sequential data stream processing  
5. Query decision (label vs. discard)  
6. Model update  
7. Performance tracking (RMSE vs. labeled samples)  

---

## Evaluation Strategy

The models and query strategies are evaluated based on:

- **Root Mean Squared Error (RMSE)**  
- **Label efficiency (learning curves)**  
- **Comparison against a random sampling baseline**  
- **Stability across multiple runs**  

---

## 📚 References

[1] Pedregosa, F. et al. (2011).  
*Scikit-learn: Machine Learning in Python.*  
Journal of Machine Learning Research, 12, 2825–2830.  

[2] Danka, T., & Horvath, P. (2018).  
*modAL: A modular active learning framework for Python.*  
arXiv:1805.00979  

[3] Bemporad, A. (2022).  
*Active Learning for Regression by Inverse Distance Weighting.*  
arXiv:2204.07177  

---

## License

This project is licensed under the **GNU General Public License v3.0 (GPL-3.0)**.

---

## Author

**[Dein Name]**


