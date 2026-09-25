# Bayesian Breast Cancer Risk Prediction

This project was developed as part of the **Bayesian Data Analysis** coursework. The primary objective is to build a predictive model to classify breast cancer risk (benign vs. malignant) while leveraging Bayesian inference to quantify parameter uncertainty through posterior distributions, rather than relying solely on classical point estimates .

## 📊 Dataset
- **Source:** Wisconsin Diagnostic Breast Cancer (WDBC) dataset from the UC Irvine Machine Learning Repository, available via Kaggle .
- **Features:** Contains attributes computed from digitized images of fine needle aspirates (FNA) of breast masses, encompassing mean measurements, standard errors, and worst-case (extreme) values across 30 numeric features .
- **Target Variable:** Binary outcome indicating cancer diagnosis ($1 = \text{malignant}$, $0 = \text{benign}$) .

## ⚙️ Methodology
1. **Bayesian Logistic Regression:** Formulating a binary logistic regression model under a Bayesian framework using a Bernoulli likelihood with a logit link function
2. **Prior Specification:** Assigning weakly informative Normal priors ($N(0, \sigma^2)$) to the regression coefficients to stabilize estimation and allow data to dominate inference
3. **Posterior Inference & MCMC:** Utilizing Markov Chain Monte Carlo (MCMC) sampling via HMC/NUTS to approximate the intractable posterior distribution
4. **Convergence Diagnostics:** Assessing chain convergence using Gelman-Rubin potential scale reduction factors (PSRF) and Geweke diagnostics
5. **Model Evaluation:** Evaluating performance via posterior predictive checks, confusion matrix metrics (Accuracy, Sensitivity, Specificity), and the Receiver Operating Characteristic (ROC) curve with AUC

## 📈 Results & Findings
- **Model Performance:** Achieved an overall classification accuracy of **94.55%** and an outstanding Area Under the ROC Curve (AUC) of **0.9867** .
- **Clinical Metrics:** Recorded a sensitivity of **89.62%** (identifying malignant cases) and a specificity of **97.48%** (classifying benign cases) .
- **Parameter Insights:** Posterior analysis indicated that features such as texture mean, radius mean, and concave points exhibit strong positive associations with malignancy risk .
- **Convergence:** Both Gelman-Rubin diagnostics (PSRF equal to 1) and Geweke Z-scores confirmed successful and stable MCMC chain convergence .

## 🛠️ Tech Stack
- **Language:** R (R Markdown, R Scripts)
- **Libraries/Frameworks:** 
  - Probabilistic Programming / MCMC: `JAGS`
  - Data Manipulation & Metrics: `tidyverse`, `pROC`
  - Visualization: `ggplot2`

## 📂 Project Structure
```text
├── code/                  # R Markdown, HTML reports, and R source files
├── presentation/          # Slide presentation files
├── paper/                 # Research paper documentation (PDF)
├── dataset.csv            # Wisconsin Diagnostic Breast Cancer dataset
├── README.md              # Project documentation
└── requirements.R         # R package dependencies (or renv.lock)
