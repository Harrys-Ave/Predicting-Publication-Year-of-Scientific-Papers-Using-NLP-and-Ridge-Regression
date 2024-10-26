# Skills and Tech Stack

This file summarizes the skills, technologies, and methodologies utilized in the project "Predicting the Year of Publication for Scientific Papers."

## Key Skills and Techniques

- **Data Cleaning and Imputation**:
  - Used `SimpleImputer` with a 'constant' strategy for efficient handling of missing data.
  - Removed outliers and duplicates based on thorough data inspection.

- **Natural Language Processing (NLP)**:
  - Applied NLP techniques to preprocess text data from titles, abstracts, and publisher information.
  - Used `HashingVectorizer` for vectorization, selecting different `ngram_range` values to capture meaningful patterns in the data.
  - Experimented with stop word removal and dimensionality reduction to balance computational efficiency with text feature relevance.

- **Feature Engineering**:
  - Engineered meaningful features by transforming text data into numerical formats with NLP vectorizers.
  - Reduced dimensions of feature space using TruncatedSVD due to computational constraints.

- **Machine Learning Modeling**:
  - Explored various regression models, with Ridge Regression achieving the best performance based on Mean Absolute Error (MAE).
  - Conducted hyperparameter tuning with `RandomizedSearchCV` to optimize model parameters.

- **Evaluation Techniques**:
  - Evaluated models using MAE, prioritizing accuracy and computational efficiency.
  - Implemented thorough validation to ensure robust performance metrics.

## Technologies and Libraries

- **Languages**:
  - Python 3.x

- **Libraries**:
  - `scikit-learn`: For modeling, vectorization, and evaluation.
  - `nltk`: Assisted with stop word handling in NLP preprocessing.
  - `numpy`, `pandas`: Data manipulation and handling.
  - `matplotlib`: Visualization of results and preprocessing steps.

---
