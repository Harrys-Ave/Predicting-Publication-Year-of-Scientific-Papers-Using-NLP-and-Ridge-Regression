# Year of Publication Prediction

**Author**: Harry Averkiadis  
**Project Focus**: Predicting the year of publication for scientific papers  
**File Types**: Python Notebook (.ipynb), PDF Report (.pdf)

## Project Overview
This project focuses on predicting the publication year of scientific papers using machine learning techniques and NLP preprocessing. Leveraging features like titles, abstracts, authors, and publishers, the project employs Natural Language Processing (NLP) techniques for feature extraction and Ridge Regression for optimal predictive performance.

## Files Overview
- **Machine_Learning_Challenge_Report.pdf**: Full report detailing the data preprocessing, feature engineering, model experimentation, and performance evaluation.
- **Machine_Learning_Challenge.ipynb**: Jupyter Notebook containing the code implementation, including preprocessing steps, model training, and evaluation metrics.

## Methodology

### 1. Data Preprocessing
   - **Missing Data Handling**: Missing values were handled using `SimpleImputer` with the strategy set to `'constant'`. The `'editor'` feature was dropped due to high missing value rates, and duplicates were removed based on the `'title'`.
   - **Outlier and Duplicate Removal**: Boxplot inspection was used to identify outliers, which were retained to avoid overfitting. Duplicates were removed based on title similarity.
   - **Data Types and Transformations**: The `year` was cast to integer, while other features were converted from lists to strings.  

### 2. NLP Feature Engineering
   - **Vectorization**: TFidf, Count, and Hashing Vectorizers were tested; Hashing Vectorizer was selected with ngram configurations per feature to capture specific word patterns.
   - **Dimensionality Reduction**: Due to computational constraints, TruncatedSVD was employed with `n_components=90`.
   - **Stop Word Removal and Clipping**: Stopwords were removed with no substantial impact on MAE; the `year` feature was clipped to a maximum of 2023.

### 3. Data Split
   - 80% of the data was used for training and 20% for validation. After model evaluation, the sets were recombined for final tuning. 
   
### 4. Model Selection and Training
   - **Model Candidates**: A variety of models were tested, including Ridge, Lasso, ElasticNet, Random Forest, Gradient Boosting, AdaBoost, SVR, and MLP regressors.
   - **Best Model**: Ridge Regression achieved the lowest MAE of 3.2 on the validation set, selected for its balance of accuracy and efficiency.
   
### 5. Hyperparameter Tuning
   - **RandomizedSearchCV**: Chosen for hyperparameter tuning to balance computational demands and efficiency, confirming Ridge’s default solver and alpha parameters as optimal.

## Results and Findings
- **Best Model Performance**: Ridge Regression, with MAE of 3.2, showed the highest accuracy and computational efficiency.
- **Dimensionality Reduction**: TruncatedSVD was applied to reduce feature dimensions, though computational constraints limited its effectiveness in the current setup.

## References
- Scikit-Learn Documentation: [https://scikit-learn.org/stable/index.html](https://scikit-learn.org/stable/index.html)

### Requirements
- Python 3.x
- Jupyter Notebook
- Libraries: `scikit-learn`, `numpy`, `pandas`
