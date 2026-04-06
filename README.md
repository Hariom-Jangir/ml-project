# 🍽️ Recipe Recommendation System (RCCIPR Project)

## 📌 Overview

The **Recipe Recommendation System** is a Machine Learning project that suggests recipes to users based on ingredients, cuisine, and cooking time.
It uses multiple ML techniques like **TF-IDF, KNN, Cosine Similarity, and K-Means Clustering** to provide accurate and personalized recommendations.

---

## 🎯 Objectives

* Recommend recipes based on:

  * Similar ingredients
  * Cuisine type
  * Cooking time
* Provide multiple recommendation approaches:

  * Recipe-based
  * Cluster-based
  * Custom input-based
* Visualize recipe clusters using PCA

---

## 🧠 Machine Learning Concepts Used

* **TF-IDF (Term Frequency – Inverse Document Frequency)**
* **One-Hot Encoding (for cuisine)**
* **MinMax Scaling (for cooking time)**
* **Cosine Similarity & Euclidean Distance**
* **K-Nearest Neighbors (KNN)**
* **K-Means Clustering**
* **Principal Component Analysis (PCA)**

---

## 📂 Dataset

The dataset contains recipe information with the following columns:

* `name` → Recipe name
* `ingredients` → List of ingredients
* `cuisine` → Type of cuisine
* `time` → Cooking time (in minutes)

---

## ⚙️ Project Workflow

1. **Data Preprocessing**

   * Handle missing values
   * Clean text data
   * Normalize cooking time

2. **Feature Engineering**

   * Convert ingredients → TF-IDF vectors
   * Encode cuisine → One-hot encoding
   * Scale time → MinMaxScaler

3. **Model Building**

   * Compute similarity matrices
   * Apply KNN for recommendations
   * Perform K-Means clustering

4. **Recommendation System**

   * By recipe name
   * By custom user input
   * By cluster similarity

5. **Visualization**

   * PCA for 2D cluster visualization

---

## 🚀 Features

✔ Recommend recipes based on similar dishes
✔ Custom input-based recommendations
✔ Cluster-based suggestions
✔ Interactive CLI interface
✔ PCA visualization of clusters

---

## 🖥️ How to Run

### 1. Install dependencies

```bash
pip install pandas numpy scikit-learn matplotlib
```

### 2. Place dataset

Ensure your dataset file is named:

```
ml_recipe.csv
```

### 3. Run the program

```bash
python your_script_name.py
```

---

## 🎮 Usage

Choose from the menu:

1. Recommend by recipe name
2. Recommend using custom ingredients
3. Cluster-based recommendation
4. Exit

---

## 📊 Example Input

**Custom Input:**

```
Ingredients: chicken garlic butter
Cuisine: indian
Time: 30
```

**Output:**

```
Top Recommendations:
- Butter Chicken
- Chicken Curry
- Chicken Tikka
```

---

## 📈 Output Visualization

* PCA scatter plot showing recipe clusters
* Saved as: `cluster_pca.png`

---

## 🏆 Advantages

* Handles large ingredient datasets
* Provides multiple recommendation strategies
* Easy to extend and scale

---

## ⚠️ Limitations

* Depends on dataset quality
* No real-time user feedback learning
* Limited to available cuisines

---

## 🔮 Future Improvements

* Add user ratings and feedback
* Build web interface using Streamlit
* Use deep learning for better recommendations
* Integrate real-world APIs

---

## 👨‍💻 Author

* Dhruv

---

## 📚 References

* Scikit-learn documentation
* Machine Learning course materials
* Online datasets (Kaggle)

---

## ⭐ Conclusion

This project demonstrates how Machine Learning can be used to build an intelligent recommendation system by combining text processing, similarity measures, and clustering techniques.

---
