# Uplift Modeling for SMS Targeting
Customer segmentation and uplift modeling to optimize SMS targeting under budget constraints


## Overview
When marketing budgets are limited, the goal is not to target customers who will visit anyway—but those whose behavior changes because of the message.

This project uses uplift modeling and customer segmentation to identify which customers should receive SMS messages to maximize **incremental store visits**.

---

## Business Problem
If SMS budget is limited, how can we maximize incremental store visits compared to sending no SMS?

This is a **causal inference and targeting problem**, not just a prediction problem.

---

## Dataset
- BIGTARGET dataset (LENTA + Microsoft)
- 687,029 customers
- 196 features
- Includes:
  - Customer behavior (spending, frequency)
  - Treatment indicator (SMS received)
  - Outcome (store visit)

---

## Methodology

### 1. Data Preprocessing
- Cleaned missing/invalid values  
- Removed high-missing and zero-dominant features  
- Applied log transformations  
- Standardized features  

### 2. Dimensionality Reduction
- PCA used to reduce high-dimensional behavioral space  

### 3. Customer Segmentation
- K-means clustering (k=4)
- Segments identified:
  - Sure Things
  - Persuadables
  - Weaker Persuadables
  - Lost Causes  

### 4. Uplift Analysis
- Compared treated vs control within each segment  
- Measured **incremental lift**

### 5. Model Validation
- 4-class Random Forest (95% accuracy)  
- Binary Persuadables model (AUC ≈ 0.9967)

---

## Key Results

- Segment 2 (Persuadables) had the highest uplift (~0.80%)  
- Segment 3 also showed positive uplift (~0.59%)  
- Segment 1 had high baseline visits but low incremental value  
- Segment 4 had low engagement and weak returns  

Not all customers should be targeted.

---

## Business Impact

Instead of mass messaging:
- Prioritize **Segment 2**
- Expand to **Segment 3**
- Avoid overspending on low-impact groups  

This improves ROI under budget constraints.

---

## Tech Stack
- R (tidyverse, caret, ranger)
- PCA (irlba)
- Machine Learning (Random Forest)
- Data Visualization (ggplot2)

---

## Project Structure
- `/notebooks/` → Analysis code  
- `/images/` → Visualizations  
- `/report/` → Final report  

---

## Full Report
See full analysis here:  
`/report/Final_Report.pdf`
