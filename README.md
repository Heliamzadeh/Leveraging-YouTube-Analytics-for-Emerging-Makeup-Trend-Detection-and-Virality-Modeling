# Leveraging YouTube Analytics for Emerging Makeup Trend Detection and Virality Modeling

**Advanced Machine Learning · Deep Learning Concepts · Applied Data Science · Predictive Analytics**

---

## Overview

This project develops an **end-to-end machine learning system** to detect **emerging makeup trends**, **predict content virality**, and **support data-driven influencer and marketing decisions** using large-scale **YouTube analytics data**.

By transforming raw, unstructured social media signals into structured predictive features, the project demonstrates how **modern machine learning pipelines** can be applied to real-world marketing intelligence problems. The work integrates **feature engineering, supervised learning, ensemble methods, and model interpretability**, moving beyond descriptive analytics toward **actionable decision support**.

---

## Problem Statement

Beauty brands and digital marketers face significant uncertainty when:
- Identifying early-stage trends
- Selecting high-impact influencers
- Forecasting content performance before virality occurs

Traditional market research approaches are often **slow, reactive, and expensive**.  
This project addresses these challenges by answering:

- Which makeup-related content is likely to achieve high engagement?
- What content features drive virality on YouTube?
- Can engagement be predicted early using machine learning models?
- How can brands systematically evaluate creator performance?

---

## Data Collection

### Data Source
- **YouTube Data API**
- Large-scale dataset of makeup-related videos
- Randomized query strategy to reduce sampling bias
- Data collected across multiple time windows (2024–2025)

### Raw Data Features
- View count, like count, comment count
- Video title, description, tags
- Upload timestamp
- Video duration
- Channel metadata (e.g., country)

---

## Feature Engineering

Advanced preprocessing and feature construction were applied to transform raw data into **model-ready representations**:

### Engagement Engineering
- Log-transformation of heavy-tailed engagement metrics
- Normalized engagement rate:
  
  \[
  \text{Engagement Rate} = \frac{\text{Likes} + \text{Comments}}{\text{Views}}
  \]

### Temporal Features
- Upload hour encoding
- Time-based aggregation
- Duration binning (short / medium / long)

### Linguistic Proxies (NLP-Inspired)
- Title length
- Keyword density
- Metadata richness indicators

### Target Construction
- Quantile-based labeling for multi-class virality prediction
- Binary and multi-class engagement targets

---

## Modeling Approach

### Learning Objectives
- **Classification**: Predict high-engagement vs low-engagement content
- **Regression**: Estimate continuous engagement outcomes
- **Ranking**: Identify high-potential videos before full virality

### Algorithms Implemented

#### Baseline Models
- Logistic Regression (interpretable benchmark)

#### Ensemble & Advanced Models
- Random Forest Classifier
- **XGBoost (Gradient Boosted Trees)**  
  - Handles nonlinear interactions  
  - Robust to heterogeneous feature scales  
  - Strong performance under class imbalance  

### Training Strategy
- Stratified train / validation / test split (70 / 15 / 15)
- Cross-validated hyperparameter tuning
- Metric-driven optimization:
  - ROC-AUC
  - Precision–Recall AUC
  - F1-score

---

## Model Evaluation

### Performance Highlights
- Accuracy ≈ **85%**
- ROC-AUC ≈ **0.94**
- Strong generalization on unseen test data
- Stable performance under class imbalance

### Diagnostics
- Confusion matrix analysis
- ROC curve inspection
- Feature correlation analysis

---

## Interpretability & Explainability

To ensure **business usability**, the project integrates multiple explainability techniques:

### Feature Importance
- Tree-based gain importance
- Permutation importance (performance degradation analysis)

### Partial Dependence Analysis
- Impact of video duration on engagement probability
- Upload timing effects
- Nonlinear saturation effects in view counts
- Optimal title length ranges

These methods translate model predictions into **clear strategic insights**, avoiding black-box decision-making.

---

## Business Impact

### For Beauty Brands
- Early detection of emerging makeup trends
- Reduced product launch risk
- Quantitative influencer selection

### For Marketing Teams
- Content optimization strategies
- Posting-time recommendations
- Performance-driven campaign planning

### For Analytics Teams
- Scalable ML pipeline reusable across domains
- Reproducible modeling framework
- Strong foundation for real-time trend monitoring systems

---

## Technical Stack

### Languages
- Python

### Libraries & Frameworks
- pandas, numpy
- scikit-learn
- xgboost
- matplotlib, seaborn
- scipy
- YouTube Data API

### Core Skills Demonstrated
- Supervised machine learning (classification & regression)
- Gradient boosting optimization
- Feature engineering for behavioral data
- Model validation under class imbalance
- Post-hoc interpretability techniques
- Applied ML for strategic decision-making

---

## Repository Structure

```text
├── PHASE1_INSY662_Group1.ipynb    # Data collection & exploratory analysis
├── PHASE2_INSY662_Group1.ipynb    # Feature engineering & ML modeling
├── INSY662_ProgressReport.pdf    # Methodology, results, and interpretation
├── README.md
