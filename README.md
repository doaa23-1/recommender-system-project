# 🎬 Movie Recommendation System using Content-Based Filtering

This project focuses on building a content-based movie recommendation system using metadata from the Netflix Movies and TV Shows dataset. The system recommends similar movies by analyzing textual features such as genres, cast, directors, and descriptions using TF-IDF vectorization and K-Nearest Neighbors (KNN).

This work was completed as a team project for the course **CCAI-422 – Recommender Systems**.

---

## 🎯 Project Objective

- Build a recommendation system using content-based filtering.
- Extract useful features from movie metadata.
- Calculate similarity using cosine similarity.
- Tune KNN hyperparameters for best recommendation performance.
- Evaluate results using Precision@K and MSE.

---

## 🧪 Dataset

- **Source:** Kaggle — *Netflix Movies and TV Shows Dataset*
- **Total Titles:** 8,807
- **Features Used:**
  - Title  
  - Director  
  - Cast  
  - Listed Genres  
  - Description  

A combined **content** field was created by merging multiple text features for vectorization.

---

## 🛠️ Methodology

### 1️⃣ Preprocessing  
- Handle missing values (drop/fill).
- Create a “content” column combining textual metadata.

### 2️⃣ Feature Engineering  
- Apply **TF-IDF Vectorization** with:
  - max_features: 5000 / 7000 / 10000  
  - n-grams: (1, 2)

### 3️⃣ Modeling  
- Use **K-Nearest Neighbors (KNN)** with **cosine similarity**.
- Retrieve the top K most similar movies for any given title.

### 4️⃣ Hyperparameter Tuning  
- Tested K values: **5, 10, 15, 20**
- Tested TF-IDF max features: **5000, 7000, 10000**

### 5️⃣ Evaluation Metrics  
- **Precision@K (P@K)**
- **Mean Squared Error (MSE)**

---

## 📊 Results

| Configuration                  | Precision | MSE     |
|-------------------------------|-----------|---------|
| Initial model (K=10)          | 0.50      | 0.092   |
| Tuned model (K=5, features=5000) | **1.00** | 0.107   |

✅ Achieved **Precision@5 = 1.0**, meaning all recommendations were relevant.  
⚠️ MSE slightly increased due to tighter clustering.

---

## 🔍 Insights

- Smaller K values increase precision but reduce diversity.
- Larger K values create more variety but lower relevance.
- Brute-force KNN faces scalability issues for large datasets.
- Content-based filtering struggles with:
  - Cold start problem  
  - Sparse metadata  
  - Lack of user interaction data  

Future improvements may include hybrid filtering and dimensionality reduction.

---

## 🛠️ Technologies Used

- Python  
- Scikit-learn  
- TF-IDF Vectorizer  
- KNN (NearestNeighbors)  
- Cosine Similarity  
- Google Colab  

---

## 👥 Team Members

- **Doaa Brnawi**
- **Lamis Melebari**  
- **Taif Alharbi**  

---

## 📚 References

- **Netflix Movies and TV Shows Dataset** – Kaggle.  
- Rakesh, S. (2024). *Movie Recommendation System Using Content-Based Filtering*.  
- Goyani, M., & Chaurasiya, N. (2020). *A Review of Movie Recommendation Systems*.  
- Delimayanti, L., Yuliani, A., & others. (2022). *Content-Based Filtering with KNN for Movie Recommendation Systems*.  

