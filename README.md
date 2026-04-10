# 🍽️ Recipe Recommendation System
### PRML Course Project

A machine learning–powered recipe recommendation system built with Python. Given a recipe name or a custom set of ingredients, cuisine, and cooking time, the system finds the most similar recipes from the dataset using a combination of text vectorization, dimensionality reduction, clustering, classification, and similarity metrics.

---

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [ML Pipeline](#ml-pipeline)
- [Techniques Used](#techniques-used)
- [Project Structure](#project-structure)
- [Requirements](#requirements)
- [How to Run](#how-to-run)
- [Usage](#usage)
- [Results](#results)

---

## Project Overview

This project implements an end-to-end recipe recommendation system as part of the Pattern Recognition and Machine Learning (PRML) course. The system:

- Processes raw recipe data (ingredients, cuisine, cooking time)
- Engineers features using NLP and encoding techniques
- Reduces dimensionality with PCA
- Clusters recipes with KMeans
- Classifies cuisine with a KNN classifier
- Recommends similar recipes using Cosine Similarity and Euclidean Distance

Two recommendation modes are supported:
1. **By Recipe Name** — find recipes similar to a known dish
2. **Custom Query** — specify your own ingredients, cuisine, and time budget

---

## Dataset

**File:** `ml_recipes.csv`  
**Size:** ~1,000 recipes

| Column | Type | Description |
|---|---|---|
| `name` | string | Name of the recipe |
| `ingredients` | string | Space-separated list of ingredients |
| `cuisine` | string | Cuisine type (e.g., Indian, Italian, Mexican) |
| `time` | integer | Cooking time in minutes |

**Sample rows:**

| name | ingredients | cuisine | time |
|---|---|---|---|
| Tomato Curry | tomato onion butter garlic | Indian | 30 |
| Pasta Alfredo | pasta cream cheese garlic | Italian | 25 |
| Chicken Tacos | chicken tortilla onion cilantro lime | Mexican | 30 |

---

## ML Pipeline

```
Raw CSV Data
     │
     ▼
Data Loading & Cleaning
     │
     ▼
Feature Engineering
  ├── TF-IDF on ingredients (text → numerical)
  ├── One-Hot Encoding on cuisine (categorical → binary)
  └── MinMax Scaling on cooking time (normalization)
     │
     ▼
PCA — Dimensionality Reduction (50 components)
     │
     ├──────────────────────────────────┐
     ▼                                  ▼
KMeans Clustering             KNN Classifier
(unsupervised grouping)    (cuisine prediction, 5-fold CV)
     │                                  │
     └──────────────┬───────────────────┘
                    ▼
         Similarity Computation
      ├── Cosine Similarity Matrix
      └── Euclidean Distance Matrix
                    │
                    ▼
         Recommendation Engine
      ├── Recommend by Name
      └── Recommend by Custom Query
```

---

## Techniques Used

| Technique | Library | Purpose |
|---|---|---|
| **TF-IDF Vectorization** | `sklearn` | Convert ingredient text to numerical features |
| **One-Hot Encoding** | `sklearn` | Encode categorical cuisine labels |
| **MinMax Scaling** | `sklearn` | Normalize cooking time to [0, 1] |
| **PCA** | `sklearn` | Reduce feature dimensions, retain max variance |
| **KMeans Clustering** | `sklearn` | Group recipes by cuisine/ingredient similarity |
| **KNN Classifier** | `sklearn` | Predict cuisine; evaluate via 5-fold cross-validation |
| **Cosine Similarity** | `sklearn` | Measure recipe similarity by feature angle |
| **Euclidean Distance** | `sklearn` | Measure recipe similarity by feature distance |

---

## Project Structure

```
.
├── Prml_Project.ipynb      # Main Jupyter Notebook (full pipeline)
├── ml_recipes.csv          # Dataset (1000 recipes)
└── README.md               # This file
```

---

## Requirements

Install the required packages with:

```bash
pip install numpy pandas scikit-learn scipy jupyter
```

**Python version:** 3.7+

---

## How to Run

1. **Clone or download** this repository.

2. **Place both files** (`Prml_Project.ipynb` and `ml_recipes.csv`) in the same directory.

3. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook Prml_Project.ipynb
   ```

4. **Run all cells** in order (`Kernel → Restart & Run All`).

5. The interactive recommendation menu will launch in the final cell.

---

## Usage

### Interactive Menu (Cell 29)

When the notebook finishes running, you will see:

```
==================================================
   RECIPE RECOMMENDATION SYSTEM READY
==================================================

  1. Recommend by recipe name
  2. Custom recommendation (ingredients + cuisine + time)
  3. Exit
```

**Option 1 — By Recipe Name:**
```
Enter recipe name: chicken curry
```
Returns the top similar recipes ranked by cosine similarity and euclidean distance.

**Option 2 — Custom Query:**
```
Enter ingredients: tomato onion garlic
Enter cuisine: Indian
Enter cooking time (minutes): 30
```
Transforms the query through the full pipeline and returns the closest matching recipes.

---

## Results

- **KNN Cuisine Classification** — evaluated using 5-fold cross-validation; accuracy printed during training as:
  ```
  [INFO] KNN 5-Fold Accuracy: XX.XX% +/- X.XX%
  ```
- **PCA** — retains variance summary printed as:
  ```
  [INFO] PCA: 50 components, XX.X% variance retained
  ```
- **KMeans** — number of clusters equals the number of unique cuisines in the dataset, printed as:
  ```
  [INFO] KMeans: N clusters
  ```

---

## Course Information

**Course:** Pattern Recognition and Machine Learning (PRML)  
**Course Code:** CSL2050 — S2026  
**Instructor:** Avinash Sharma  
**Notebook:** `Prml_Project.ipynb`  
**Dataset:** `ml_recipes.csv`
