 
# TMDB Movie Revenue Prediction and Commercial Performance Analysis

## 1. Project Overview

This project uses movie data collected from **The Movie Database (TMDB) API** to analyze movie characteristics and apply machine learning techniques for two tasks:

1. **Movie Revenue Prediction (Regression):** Predicting movie revenue based on selected movie features.
2. **Movie Success Classification:** Classifying movies as successful or unsuccessful based on their revenue-to-budget ratio.

The project follows an end-to-end machine learning workflow, including data collection, data cleaning, exploratory data analysis, feature engineering, feature selection, model training, hyperparameter tuning, evaluation, model comparison, and final pipeline development.

## 2. Dataset

The dataset was collected using the TMDB API.

- **Source:** [The Movie Database (TMDB)](https://www.themoviedb.org/)
- **Final Dataset Size:** 4,583 movies
- **Collection Period:** 2000–2025

The collected movie records include information such as:

- Movie title and release date
- Budget and revenue
- Runtime
- Original language
- Genres
- Production countries
- Cast information
- Keywords
- Production companies
- Financial Logs

The dataset was cleaned and preprocessed before being used for machine learning.

**Important:** The final preprocessed dataset, `tmdb_movies_preprocessed.csv`, is provided separately in the project repository.

## 3. Machine Learning Tasks

### Regression: Movie Revenue Prediction

The regression task predicts movie revenue using selected movie features.

The target variable is `revenue_log`, which represents the log-transformed movie revenue.

Different regression models were experimented with, compared, and tuned. XGBoost was selected as the final regression model.



### Classification: Movie Success Prediction

The classification task predicts whether a movie is successful or unsuccessful.

A movie is classified as successful when its revenue is at least twice its budget:

- **Successful (1):** Revenue ≥ 2 × Budget
- **Unsuccessful (0):** Revenue < 2 × Budget

Different classification models were experimented with and evaluated. Extra Trees was selected as the final classification model.


## 4. Machine Learning Workflow

The project follows these main stages:

1. TMDB data collection
2. Data cleaning and preprocessing
3. Exploratory Data Analysis (EDA)
4. Feature engineering
5. Feature selection
6. Training and testing data preparation
7. Regression model development
8. Classification model development
9. Hyperparameter tuning and model optimization
10. Model evaluation and comparison
11. Final pipeline development
12. Model saving

### Final Selected Models

| Task | Selected Model |
|---|---|
| Regression | XGBoost Regressor |
| Classification | Extra Trees Classifier |

### Final Machine Learning Pipelines

Separate scikit-learn pipelines were developed for both tasks.

Each pipeline includes:

- Feature selection using `ColumnTransformer`
- Missing value handling using `SimpleImputer` with median strategy
- The selected trained machine learning model

The final pipelines were saved as:

- `final_movie_revenue_pipeline.pkl`
- `movie_success_classification_pipeline.pkl`

These pipelines start with the selected, engineered movie features. The earlier data collection and feature engineering stages are performed separately in the notebook.

## 5. Project Files

The project repository contains the Jupyter notebooks and supporting datasets required to run the analysis.

Important files include:

| File | Description |
|---|---|
| `TMDB_Movie_Project_phase_2 (Final).ipynb` |  project notebook  
| `tmdb_movies_preprocessed.csv` | Final preprocessed movie dataset |
| `final_movie_revenue_pipeline.pkl` | Saved regression pipeline |
| `movie_success_classification_pipeline.pkl` | Saved classification pipeline |

*Note: Use the actual filenames present in the downloaded repository if notebook or supporting file names differ.*

## 6. Software and Libraries

The project was developed using Python 3.15.0 in a virtual environment (`.venv`).

The following libraries and tools were used:

| Package / Tool | Purpose |
|---|---|
| Python 3.15.0 | Programming language |
| Jupyter Notebook | Running the project notebooks |
| IPykernel | Connecting the virtual environment to Jupyter |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical computations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Scikit-learn | Machine learning, preprocessing, feature selection and evaluation |
| XGBoost | Regression model |
| Requests | Making TMDB API requests |
| Graphviz Python package | Creating machine learning workflow diagrams |

## 7. Installation and Environment Setup

A Python virtual environment was created to manage project dependencies separately.

### Step 1: Clone the repository

```bash
git clone https://github.com/mahhek/tmdb_dstt_project.git

cd tmdb_dstt_project
```

### Step 2: Create and activate a virtual environment

```bash
python3 -m venv .venv

source .venv/bin/activate
```

### Step 3: Install the required libraries

```bash
python -m pip install --upgrade pip

python -m pip install ipykernel jupyter pandas numpy requests matplotlib seaborn scikit-learn xgboost graphviz
```

### Step 4: Register the Jupyter kernel

```bash
python -m ipykernel install --user --name tmdb --display-name "Python (TMDB Project)"
```

### Step 5: Open Jupyter Notebook

```bash
jupyter notebook
```

Select the **Python (TMDB Project)** kernel when running the notebook.

### Optional: Graphviz System Installation

The Graphviz Python package requires the Graphviz system executable (`dot`) to render diagrams.

On macOS, it can be installed using Homebrew:

```bash
brew install graphviz
```

## 8. Important Instructions for Running the Notebook

**Important:** The notebook contains a `KeyboardInterrupt` error in the TMDB API data collection section.

This occurred because movie records were downloading very slowly, so the execution was manually stopped. We decided to use the 4,583 movies collected up to that point as our final dataset.

This was intentional. No further data collection is required.

Please follow these instructions before running the notebook:

1. Do not execute the TMDB API data collection cells.
2. Do not make fresh TMDB API requests.
3. Use the provided preprocessed dataset, `tmdb_movies_preprocessed.csv`.
4. Place the CSV file in the same directory as the notebook.
5. Execute the initial setup and configuration cells to define the required variables and functions.
6. Start execution from **Step 5: Financial Data Quality Assessment and Dataset Preparation**, where the preprocessed CSV is loaded.
7. Continue with feature engineering, feature selection, model training, hyperparameter tuning, and evaluation.

The data collection process takes more than 8 hours. Repeating it is unnecessary because the collected data and supporting files are already provided.

## 9. Important Notes

- The provided dataset should be used instead of collecting movie records again.
- Do not delete or overwrite the provided CSV files.
- Make sure the required libraries are installed before running the notebooks.
- Execute the notebook cells in the correct order.
- The saved machine learning pipelines use the selected engineered features as input.

## 10. Conclusion

This project applies machine learning techniques to TMDB movie data for revenue prediction and movie success classification.

After data preparation, exploratory analysis, feature engineering, feature selection, model experimentation, and hyperparameter tuning, XGBoost was selected for regression and Extra Trees for classification.

Both models were evaluated using appropriate performance metrics. Separate machine learning pipelines were also developed and saved for future use.

The project covers the major stages of a machine learning workflow, from preparing movie data to developing and evaluating the final models.

## 11. Repository

**GitHub:** https://github.com/mahhek/tmdb_dstt_project

**Data Source:** https://www.themoviedb.org/

This product uses the TMDB API but is not endorsed or certified by TMDB.
