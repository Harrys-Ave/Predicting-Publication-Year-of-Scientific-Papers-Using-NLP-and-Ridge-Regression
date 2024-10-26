# Year of Publication Prediction

**Author**: Harry Averkiadis  
**Project Focus**: Predicting the year of publication for scientific papers  
**File Types**: Python Notebook (.ipynb), PDF Report (.pdf)

## Project Overview
This machine learning project is dedicated to predicting the year of publication for scientific papers based on metadata attributes, such as title, author, publisher, and abstract. Various machine learning algorithms were tested for performance, with Ridge Regression proving most effective for the prediction task.

## Files Overview
- **Machine_Learning_Challenge_Report.pdf**: Full report detailing the data preprocessing, feature engineering, model experimentation, and performance evaluation.
- **Machine_Learning_Challenge.ipynb**: Jupyter Notebook containing the code implementation, including preprocessing steps, model training, and evaluation metrics.

## Methodology

### 1. Data Preprocessing
   - **Missing Data Handling**: Missing values were handled using `SimpleImputer` with the strategy set to `'constant'`. The `'editor'` feature was dropped due to high missing value rates, and duplicates were removed based on the `'title'`.
   - **Outlier Handling**: Outliers in the `'year'` feature were identified through visual inspection but retained to avoid overfitting.
   - **Data Types and Transformations**: The `year` was cast to integer, while other features were converted from lists to strings.  
   
### 2. Feature Engineering
   - **Vectorization Techniques**: TFidf, Count, and Hashing Vectorizers were tested; Hashing Vectorizer was selected with ngram configurations per feature to capture specific word patterns.
   - **Data Split**: 80% of the data was used for training and 20% for validation. After model evaluation, the sets were recombined for final tuning.
   - **Encoding**: Stopwords were removed with no substantial impact on MAE; final configurations optimized for computational efficiency.  
   
### 3. Model Selection and Training
   - **Model Candidates**: A variety of models were tested, including Ridge, Lasso, ElasticNet, Random Forest, Gradient Boosting, AdaBoost, SVR, and MLP regressors.
   - **Best Model**: Ridge Regression achieved the lowest MAE of 3.2 on the validation set, selected for its balance of accuracy and efficiency.
   
### 4. Hyperparameter Tuning
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
