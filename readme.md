# Cinema Insights: Unlocking Trends in IMDb Movie Data

## Introduction
The film industry is highly competitive, and understanding what drives a movie's success is crucial. This project leverages the IMDb public dataset on BigQuery to analyze factors such as genres, runtime, ratings, cast, and crew. The objective is to uncover actionable insights for filmmakers, producers, and marketers to optimize creative and financial decisions.

## Business Problem
- **Challenge**: Only a fraction of movies achieve critical and commercial success. Understanding the factors influencing popularity and profitability is essential for informed decisions in production, marketing, and casting.
- **Objective**: Analyze IMDb data to identify elements impacting audience ratings, critical reception, and revenue.
- **Expected Outcome**: Provide actionable insights to enhance movie success.

---

## Data Overview
- **Dataset Source**: IMDb Public Dataset from BigQuery
- **Key Tables**:
  - `title_basics`: Movie details (genres, runtime, release year)
  - `title_ratings`: Audience ratings
  - `title_principals`: Cast and crew information
  - `title_crew`: Directors and writers
  - Additional Processed Files:
    - `totalscore_df.csv`: Final movie score dataset
    - `revenue_df.csv`: Final revenue dataset

---

## Data Cleaning
- **Key Steps**:
  - Removed irrelevant columns (`job`, `characters`, etc.) to streamline analysis.
  - Imputed missing values for numeric fields like `runtime_minutes`.
  - Replaced nulls in categorical fields (e.g., `genres`) with "Unknown".
  - Used PySpark for efficient large-scale data handling.
- **Outcome**: Created a high-quality, ready-to-analyze dataset.

---

## Key Insights
1. **Genre Popularity**:
   - Drama and Comedy dominate the dataset.
   - Specialized genres like Western and Film-Noir have niche appeal.
2. **Ratings by Genre**:
   - War, Western, and Biography receive higher average ratings.
   - Horror and Reality-TV score lower.
3. **Runtime Trends**:
   - Movie runtimes increased until the 1950s, plateaued, and slightly decreased recently.
4. **Top Contributors**:
   - High-rated movies often feature specific actors and directors, emphasizing the role of talent in success.

---

## Machine Learning Models
### 1. **Random Forest**
- **Why**: Captures complex relationships and resists overfitting.
- **Implementation**:
  - Training/testing split: 80/20
  - Features: Genre, runtime, popularity, and sentiment
  - Evaluation: RMSE and cross-validation
- **Insights**: Genres, director scores, and sentiment significantly influence revenue.

### 2. **XGBoost**
- **Why**: High efficiency and handles missing data well.
- **Implementation**:
  - Similar features as Random Forest
  - Performance Metrics: Training/testing scores
- **Insights**: Popularity and crew attributes align with revenue predictions.

---

## Challenges
- **Data Quality**: Missing values in critical fields like runtime and crew details.
- **High Dimensionality**: Increased computational cost for categorical features.
- **Text Analysis**: Limited by inconsistent and missing review data.

---

## Results and Strategic Implications
- **Key Findings**:
  - Runtime and genres significantly affect movie success.
  - Sentiment analysis aligns with ratings for qualitative insights.
  - Director and actor popularity correlate with profitability.
- **Implications**:
  - Predict audience reception pre-release.
  - Tailor marketing campaigns to predicted popularity.

---

## Future Scope
- Enhance with advanced NLP techniques for sentiment analysis.
- Improve data quality for more robust predictions.
- Explore causal relationships beyond correlations.

---

## How to Run the Project
1. **Data Preprocessing**:
   - Load IMDb datasets from Google Cloud Storage.
   - Perform data cleaning using PySpark.
2. **Model Training**:
   - Use `Random Forest` and `XGBoost` implementations for revenue prediction.
   - Evaluate model performance using RMSE.
3. **Analysis**:
   - Generate visualizations for insights such as genre popularity, runtime trends, and correlations.

---

## Contributors
- **Aru Pandey**
- **Raktim Verma**
- **Shiven Sharma**

---

## License
This project is licensed under the MIT License. See `LICENSE` for more details.
