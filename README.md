# RSM-m-thesis

No worries, your loyalty is appreciated, noble analyst.

Here's the revised README with the correct file references from your screenshot:

---

# Employee Sentiment and GDPR Impact — Thesis Codebase

This repository supports my master’s thesis:
**“The Mood of the Masses: A Sentimental Journey Through 8 Million Employee Reviews”**.
The thesis investigates how the EU General Data Protection Regulation (GDPR) influenced employee sentiment by analyzing millions of Glassdoor reviews. This codebase leverages natural language processing (NLP), causal inference, and econometric analysis to uncover the effects of regulatory change on workplace perception.

---

## 📁 Structure

* **`Almost done.ipynb`** – Finalized notebook integrating all major stages of the analysis.
* **`Dataset preprocess and exploration.ipynb`** – Initial data wrangling, filtering, and inspection.
* **`Exploration.ipynb` / `exploration and analysis.ipynb`** – Visual and statistical exploration of raw and cleaned datasets.
* **`Fulldataset preprocessing with metadata.ipynb`** – Preprocessing pipeline with GDPR exposure tagging and metadata enrichment.
* **`Initial sentiment.ipynb`** – Basic sentiment scoring setup and VADER sentiment baseline.
* **`METADATA API.ipynb`** – Uses GPT-4 to assess GDPR exposure from company descriptions.
* **`preliminary regression.ipynb`** – Early testing of regression models on unmatched data.
* **`rating results.ipynb`** – Analyzes structured 1–5 star ratings across treated and control groups.
* **`Under_GDPR_PSM.ipynb`** – Propensity Score Matching to balance GDPR-exposed and control firms.
* **`Under_GDPR_Sentiment.ipynb`** – Difference-in-Differences (DiD) analysis and robustness checks using sentiment scores.

---

## 🔍 Objectives

1. Preprocess millions of employee reviews and tag GDPR exposure
2. Compute sentiment scores using VADER and validate with BERT
3. Match GDPR and non-GDPR firms using Propensity Score Matching (PSM)
4. Estimate regulatory impact using Difference-in-Differences (DiD)
5. Compare structured star ratings with text-derived sentiment
6. Examine divergence as a proxy for symbolic compliance

---

## 🧮 Key Code Sections

### 1. **Preprocessing & Metadata**

* Cleaned and merged reviews, removed nulls
* Added metadata like `firm_size`, `founded_year`, `GDPR exposure` via GPT-4 prompts

### 2. **Sentiment Analysis**

* **VADER** for entire dataset
* **BERT** for a 30,000-review sample (due to computational constraints)

### 3. **Propensity Score Matching**

* Logistic model used to predict GDPR exposure
* Nearest neighbor matching applied to create a balanced treatment/control sample
### 3b. **Lags and leads model**

*  Estimates the dynamic effect of GDPR over time by including time-relative interaction terms (e.g., two years before and after implementation), allowing observation of sentiment changes before and after the policy event.
*  Tests the parallel trends assumption by examining whether pre-GDPR sentiment trajectories in treated and control groups were statistically similar, providing a robustness check for causal inference.

### 4. **Regression & Causal Analysis**

* DiD estimation run on both star ratings and sentiment scores
* Robustness checks include lags/leads models and sentiment validation

---

Major packages:

* `pandas`, `numpy`, `matplotlib`, `seaborn`
* `nltk`, `vaderSentiment`, `transformers`
* `scikit-learn`, `statsmodels`

---
