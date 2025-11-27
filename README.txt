# 🎬 Movie Recommendation Engine

A multi-algorithm recommendation system built on the MovieLens Small dataset. This project explores three distinct filtering paradigms to solve the "Information Overload" problem in entertainment.

## 📌 Project Overview
The goal was to build a system that suggests movies based on user behavior. I implemented and compared three approaches:
1.  **Statistical Correlation:** Simple Pearson correlation on user ratings.
2.  **K-Nearest Neighbors (KNN):** Unsupervised learning on a Sparse Matrix (User-Item).
3.  **Matrix Factorization (SVD):** Dimensionality reduction to extract latent features (hidden concepts).

## 🛠️ Tech Stack
* **Python 3.x**
* **Pandas & NumPy** (Data Manipulation)
* **SciPy** (Sparse Matrix calculations)
* **Scikit-Learn** (KNN & TruncatedSVD)
* **Seaborn** (Visualization of Long-Tail distribution)

## 📊 Methodology

### 1. Exploratory Data Analysis (The Long Tail)
* Merged `movies.csv` and `ratings.csv`.
* Visualized the "Long Tail" distribution, proving that 80% of movies have minimal engagement.
* **Filter:** Applied a threshold (Min 50 ratings) to remove noise and ensure statistical significance.

### 2. K-Nearest Neighbors (KNN)
* Converted the pivot table into a **Compressed Sparse Row (CSR) Matrix** to handle the sparsity of user ratings (most users have not seen most movies).
* Used **Cosine Similarity** to measure the distance between movie vectors.

### 3. Singular Value Decomposition (SVD)
* Implemented **Matrix Factorization** to compress the User-Item matrix into 12 latent components.
* This technique captures "hidden concepts" (e.g., distinguishing between "Action" and "Romance" mathematically without genre labels).

## 🚀 Results
* **Star Wars (1977)** successfully recommended *Empire Strikes Back* and *Return of the Jedi* across all algorithms.
* **KNN** provided the most precise "exact match" recommendations.
* **SVD** provided broader "conceptual" matches by reducing noise.

## 📦 How to Run
1.  Clone the repo:
    ```bash
    git clone [https://github.com/YOUR_USERNAME/movie-recommender.git](https://github.com/YOUR_USERNAME/movie-recommender.git)
    ```
2.  Install requirements:
    ```bash
    pip install pandas numpy scikit-learn scipy matplotlib seaborn
    ```
3.  Download `ml-latest-small` from GroupLens and extract `movies.csv` and `ratings.csv` to the root.
4.  Run the notebook:
    ```bash
    jupyter notebook recommender_system_main.ipynb
    ```
