# Churn Prediction Technical Test

## Overview

This repository contains the solution for a technical assessment focused on churn analysis using behavioral user data calculated over rolling 30-day windows.

The objective of the exercise was to evaluate:
- Exploratory Data Analysis (EDA)
- Outlier detection and handling
- Machine Learning modeling
- LLM + Prompt Engineering
- Conceptual Agent / RAG system design

The dataset contains user behavioral metrics such as activity, purchases and spend over the last 30 days, along with a churn target variable.

---

# Repository Structure

```bash
├── Dataset_Pruebas.csv
├── Parte 1 _ EDA.ipynb
├── Parte 2_Modelo.ipynb
├── Parte 3_ LLM + Prompting.ipynb
├── Parte 4_ Diseño de Agente_ RAG.ipynb
└── README.md
```

---

# Dataset Description

The dataset contains approximately 2,020 user records with the following variables:

| Variable | Description |
|---|---|
| user_id | Unique user identifier |
| age | User age |
| country | User country |
| events_last_30d | Number of events in the last 30 days |
| purchases_last_30d | Number of purchases in the last 30 days |
| total_spend_last_30d | Total spend in the last 30 days |
| churned | Target variable (1 = churn, 0 = active) |

The features were generated using rolling 30-day windows updated daily.

---

# Part 1 — Exploratory Data Analysis (EDA)

Notebook:
- `Parte 1 _ EDA.ipynb`

Main tasks:
- Dataset exploration
- Distribution analysis
- Correlation analysis
- Duplicate detection
- Outlier detection and interpretation
- Rolling window implications
- Data quality risk analysis

Three categories of outliers were identified:
1. Domain outliers (invalid ages)
2. Extreme statistical outliers (possible bots / logging issues)
3. Negative economic values (possible refunds or chargebacks)

---

# Part 2 — Machine Learning Model

Notebook:
- `Parte 2_Modelo.ipynb`

Models implemented:
- Logistic Regression
- Random Forest

Evaluation metrics:
- F1 Score
- ROC AUC
- Classification Report

Additional analysis:
- Feature importance
- Model limitations
- Data leakage risks
- Production improvement proposal

Main conclusion:
The available variables showed limited predictive power for churn prediction, with performance close to random classification (ROC AUC ≈ 0.5), suggesting the need for richer behavioral and historical features.

---

# Part 3 — LLM + Prompt Engineering

Notebook:
- `Parte 3_ LLM + Prompting.ipynb`

This section evaluates the use of LLMs for generating analytical summaries from ML results.

Included:
- Two prompt strategies
- Comparison between technical and business-oriented prompting
- Generated outputs
- Prompt evaluation
- Hallucination mitigation strategies

Key focus:
- Grounding
- Prompt specificity
- Structured context
- Validation of generated outputs

---

# Part 4 — Conceptual Agent / RAG Design

Notebook:
- `Parte 4_ Diseño de Agente_ RAG.ipynb`

This section presents a conceptual architecture for an AI assistant capable of answering questions such as:

> “What type of users have the highest probability of churn?”

Included:
- Conceptual RAG architecture
- Retrieval pipeline
- Vector database strategy
- Embeddings proposal
- Validation mechanisms
- Hallucination risks and mitigation

---

# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

Conceptual tools discussed:
- LLMs
- RAG
- Vector Databases
- Embeddings
- LangChain / LlamaIndex

---

# Key Findings

- Severe class imbalance (~9.5% churn)
- Weak linear correlations between features and churn
- Presence of data quality issues and outliers
- Potential temporal leakage risks due to rolling windows
- Current features are insufficient for robust churn prediction

---

# AI Usage Disclosure

Artificial Intelligence tools were used during:
- brainstorming,
- structuring explanations,
- prompt engineering,
- and reviewing analytical conclusions.

All generated outputs were manually validated against:
- Python results,
- model metrics,
- and exploratory analysis findings.

---

# Author

Technical assessment developed by:
D'Sharlie
