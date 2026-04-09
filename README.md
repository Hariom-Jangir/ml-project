# 🍽️ Recipe Recommendation System  

A machine learning-based system that recommends recipes based on ingredients, cuisine type, and cooking time using similarity measures and classification techniques.

---

## 📌 Features  

- Recommend recipes using recipe name  
- Custom recommendations using ingredients + cuisine + time  
- Uses Cosine Similarity & Euclidean Distance  
- Predicts cuisine using KNN Classifier  
- Uses PCA for dimensionality reduction  
- Groups recipes using K-Means Clustering  

---

## 📦 Package Requirements  

Install the following Python libraries:

pip install pandas numpy scikit-learn scipy

### Required Libraries:
- pandas  
- numpy  
- scikit-learn  
- scipy  
- os (built-in)  
- warnings (built-in)  

---

## 📂 Dataset  

- File name: ml_recipes.csv  
- Contains:
  - Recipe Name  
  - Ingredients  
  - Cuisine Type  
  - Cooking Time  

Custom dataset was generated using a Large Language Model (Claude AI).

---

## ▶️ Run Instructions  

Step 1: Clone the repository  
git clone https://github.com/Hariom-Jangir/ml-project.git  
cd ml-project  

Step 2: Place dataset  
Make sure ml_recipes.csv is in the same folder as the code  

Step 3: Run the project  

For Python file:
python your_file_name.py  

For Jupyter Notebook:
jupyter notebook  
Then open .ipynb file and run all cells  

---

## ⚙️ How It Works  

1. Load and preprocess dataset  
2. Convert ingredients into vectors using TF-IDF  
3. Encode cuisine using One-Hot Encoding  
4. Normalize cooking time using Min-Max Scaling  
5. Reduce dimensions using PCA  
6. Apply:
   - KNN for classification  
   - K-Means for clustering  
7. Generate recommendations using:
   - Cosine Similarity  
   - Euclidean Distance  

---

## 📊 Output  

- Top 5 similar recipes are displayed  
- Shows:
  - Recipe name  
  - Cuisine  
  - Cooking time  
  - Similarity score  

---



