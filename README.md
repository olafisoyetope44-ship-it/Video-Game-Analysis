# Video Game Sales Analysis

An exploratory data analysis and machine-learning project investigating historical video-game sales across genres, platforms, publishers, release years, and geographic markets.

## Project overview

This project uses Python to explore a video-game sales dataset containing 16,598 records and 11 columns in its original form. It combines data-quality checks, visual exploration, regional comparisons, and experiments with regression models.

**Main question:** What patterns can historical video-game sales reveal about genres, platforms, publishers, release periods, and regional markets?

## Notebook

- [Open the full analysis notebook](Video_Games_Sales_Visualization_and_Prediction_FINAL.ipynb)
- [Open in Google Colab](https://colab.research.google.com/github/olafisoyetope44-ship-it/Video-Game-Analysis/blob/main/Video_Games_Sales_Visualization_and_Prediction_FINAL.ipynb)

## Tools and techniques

- **Python:** pandas, NumPy, SciPy
- **Visualisation:** Matplotlib, Seaborn, Plotly
- **Machine learning:** scikit-learn and XGBoost
- **Analysis:** missing-value checks, descriptive statistics, grouped sales comparisons, correlation analysis, train/test split, cross-validation, and regression metrics

## Questions explored

1. How do sales and game counts vary by genre?
2. How did video-game releases vary over time?
3. How do North American, European, Japanese, and other-market sales differ by genre?
4. Which platforms have the most titles in the dataset?
5. Which publishers have the highest recorded sales by region?
6. How have annual total and average sales changed?
7. Which games have the highest recorded sales?
8. How do several regression algorithms compare on a sales-prediction task?

## Initial observations

The notebook's exploratory analysis suggests that:

- Action and Sports are prominent genres in the recorded sales data.
- Regional preferences differ; Japan's genre mix differs from North America and Europe.
- Nintendo titles and platforms feature prominently among high-selling games.
- Recorded annual sales rise through much of the 2000s before declining in later years in this dataset.

These are descriptive findings from the dataset, not guarantees about current market demand. The dataset's coverage and reporting limits should be considered when interpreting trends.

## Data preparation and modelling notes

The notebook checks missing values and removes rows with missing values before converting `Year` to an integer. It then experiments with Linear Regression, Decision Tree, Random Forest, K-Nearest Neighbours, Support Vector Regression, and XGBoost.

**Important modelling limitation:** the original model uses `NA_Sales` and `EU_Sales` as inputs to predict `Global_Sales`. Since regional sales contribute to the global total, this introduces target leakage and can produce overly optimistic test scores. These scores should not be interpreted as evidence of reliable pre-release sales forecasting. A revised modelling approach should use only information available at the intended prediction time and should fit preprocessing inside a cross-validation pipeline.

The notebook currently reads the CSV from a Google Colab sample-data path (`/content/sample_data/vgsales.csv`). That path must be adjusted or the dataset uploaded before running it in another environment.

## Running the notebook

1. Open the notebook in Google Colab using the link above.
2. Make the dataset available at the path expected by the data-import cell, or update that cell to point to your own local copy.
3. Run the notebook from top to bottom so that data preparation and model variables are created in order.

Some visualisation and machine-learning libraries may need to be installed in a fresh environment.

## Next improvements

- Make dataset loading reproducible and document the data source and licence.
- Strengthen data-quality checks, including duplicate and missing-value handling.
- Refine chart labels, units, and explanatory takeaways.
- Redesign the prediction task to avoid target leakage.
- Use preprocessing pipelines and cross-validation correctly.
- Add a concise executive summary with business-oriented recommendations.

## Skills demonstrated

Data cleaning, exploratory data analysis, data visualisation, regional and time-based comparisons, feature preparation, regression modelling, model evaluation, and communicating analytical findings.
