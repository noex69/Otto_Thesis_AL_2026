# Stream-Based Active Learning for Wood Age Prediction using FTIR Spectroscopy

This repository contains the code, notebooks, and computational environment used in the Master's thesis:

**"Active Learning Strategies for Molecular Age Prediction: A Comparative Study of Random Forest and Gradient Boosting"**

The goal of this work is to investigate the effectiveness of **stream-based active learning (AL)** for regression tasks in a chemometric setting, specifically for **molecular decay (MD) dating of wood using FTIR spectroscopy**.

---

## Project Overview

This thesis investigates the application of **Active Learning (AL)** strategies for regression in the context of **spectroscopic wood dating**.

The main objectives are:

- Predicting wood age from **ATR-FTIR spectral data** of *Pinus sylvestris*
- Comparing two **supervised learning models**:
  - **Random Forest (RF)**
  - **Gradient Boosting (XGBoost)**
- Evaluating two **Active Learning strategies**:
  - **Query-by-Committee (QBC)**
  - **Distance-based Thresholding**
- Implementing a **stream-based, single-instance AL framework**
- Assessing **label efficiency vs. predictive performance (RMSE)**

The dataset consists of wood samples from **Austria, Finland, Norway, and Poland**, covering different environmental and preservation conditions.

---

## Methodological Setting

This project operates in a **stream-based active learning setting**:

- Data arrives sequentially  
- Each instance is evaluated exactly once  
- Discarded samples are not revisited  

For each incoming observation:

- **accept (query label)** → add to training set and retrain model  
- **reject (discard)** → permanently ignored  

---

## Random Sampling Baseline

A key component of this work is the **matched-budget random sampling baseline**, used as a control condition.

- Random sampling does **not use model information**
- It isolates the effect of:

> **selection quality vs. label quantity**

### Stream-Based Constraint

In a stream-based setting, the number of labeled samples cannot be fixed in advance.

Instead, random sampling is implemented via a Bernoulli process:

p = N_AL / N_stream

Where:
- N_AL: number of samples selected by an active learning strategy  
- N_stream: total number of observations  

This ensures a **fair comparison in expectation**.

---

## Per-Configuration Baselines

Each configuration has its own random baseline:

| Model | Strategy | Baseline |
|------|--------|---------|
| RF   | QBC    | Random (p₁) |
| RF   | Threshold | Random (p₂) |
| XGB  | QBC    | Random (p₃) |
| XGB  | Threshold | Random (p₄) |

---

## Experimental Design

- 2 models × 2 strategies = **4 AL configurations**
- Each paired with a random baseline → **8 total configurations**
- Each experiment repeated across **20 random seeds**

→ **160 total runs**

---

## Evaluation Strategy

Performance is evaluated using:

- **Root Mean Squared Error (RMSE)**  
- **Learning curves (RMSE vs. labeled samples)**  
- **Label efficiency**  
- **Stability across multiple runs**  

---

## Repository Structure

### Notebooks:
01_data_preparation.ipynb
02_baseline_models.ipynb
03_active_stream_pipeline.ipynb
04_qbc.ipynb
05_analysis.ipynb
### Data:
PS20191107_2deriv_gegl
PS20191107_gegl
PS20191107_trees
### environment_list.txt
### README.md

---

## Workflow

1. Data preprocessing  
2. Train/test split  
3. Model training and tuning  
4. Stream simulation  
5. Warm-up initialization  
6. Sequential processing (accept/reject)  
7. Model update  
8. Performance tracking  

---

## Reproducibility

```bash
conda create --name <env_name> --file environment_list.txt
```

---

## References

[1] 



---

## License

This project is licensed under the **GNU General Public License v3.0 (GPL-3.0)**.

---

## Author

**[Your Name]**


