# Auspify ML Internship – Netflix Machine Learning Tasks

Machine Learning internship projects completed for **Auspify Technologies** (4-week practical program).
All four tasks use the same Netflix titles dataset (`Dataset.csv`, ~8,800 titles) and are written as Jupyter notebooks in Python.

**Author:** [abdallah atieh]
**Tools:** Python, pandas, NumPy, scikit-learn, Matplotlib, Jupyter, Git/GitHub

---

## Projects

| # | Task | Type | Main techniques |
|---|------|------|-----------------|
| 1 | [Content Recommendation System](Task1_Recommendation_System) | Recommender (Easy) | TF-IDF, cosine similarity |
| 2 | [Content Type Prediction](Task2_Content_Type_Prediction) | Binary classification (Easy) | Logistic Regression, Decision Tree, Random Forest, Gradient Boosting |
| 3 | [Audience Rating Classification](Task3_Audience_Rating_Classification) | Multi-class classification (Medium) | Decision Tree, Random Forest, GridSearchCV |
| 4 | [Content Segmentation](Task4_Content_Segmentation) | Unsupervised learning (Medium) | K-Means, PCA, Agglomerative clustering |

---

## Task summaries

### Task 1 – Netflix Content Recommendation System
Suggests similar titles from genres, director, country, type and rating.
- Cleaned placeholder values ("Not Given") and kept multi-word names as single tokens.
- Built TF-IDF vectors and ranked titles by cosine similarity. Includes a function that recommends from a user's watch history.
- **Evaluation:** genre precision@10 and genre Jaccard overlap against a random baseline (the model is far above random; scores are optimistic because genres are also model inputs, which is stated in the notebook).

### Task 2 – Content Type Prediction (Movie vs TV Show)
- **Found and removed data leakage:** `duration` ("min" vs "Season") predicts the type with 100% accuracy on its own, and genre names contained the word "TV".
- After cleaning, all four models reach about **98–99% accuracy** (majority baseline ≈ 70%).
- The strongest signal is whether a **director is listed** (TV shows rarely have one).

### Task 3 – Audience Rating Classification
- Grouped 14 ratings into **4 audience categories** (Kids, Family, Teens, Adults) because some ratings have only 3–6 titles; removed unrated titles.
- Compared 4 models and tuned Decision Tree and Random Forest with GridSearchCV (macro F1).
- Best models reach about **63% accuracy** vs a **46%** baseline. Kids and Adults are predicted best; Family and Teens are harder because the dataset has no plot or content description.

### Task 4 – Content Segmentation
- Scaled numeric features, encoded genres, and chose **K = 7** using the elbow method, silhouette score and interpretability.
- Found clear groups such as kids' TV, mature TV dramas and crime, children and family movies, documentaries, and mature action movies.
- Silhouette is about 0.20 (soft cluster borders, as expected for overlapping genres). Agglomerative clustering was used as a comparison.

---

## Repository structure

```
Auspify-ML-Internship/
├── README.md
├── Task1_Recommendation_System/
│   ├── Task1_Netflix_Recommendation_System.ipynb
│   ├── Dataset.csv
│   └── screenshots/
├── Task2_Content_Type_Prediction/
│   ├── Task2_Content_Type_Prediction.ipynb
│   ├── Dataset.csv
│   └── screenshots/
├── Task3_Audience_Rating_Classification/
│   ├── Task3_Audience_Rating_Classification.ipynb
│   ├── Dataset.csv
│   └── screenshots/
└── Task4_Content_Segmentation/
    ├── Task4_Content_Segmentation.ipynb
    ├── Dataset.csv
    └── screenshots/
```

## How to run

1. Clone or download this repository.
2. Install the libraries:
   ```
   pip install pandas numpy scikit-learn matplotlib jupyter
   ```
3. Open a task folder, open its notebook in Jupyter or VS Code, and choose **Run All**.
   Each notebook reads `Dataset.csv` from its own folder.

---

#Auspify #AuspifyTechnologies #AuspifyInternship #AuspifyProjects

