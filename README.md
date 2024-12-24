# Rotten-Tomatoes-Audience-Score-Prediction
Machine Learning model to predict audience scores or movie prices using data from Rotten Tomatoes. The project includes data analysis, feature engineering, model development (regression and classification), and evaluation through advanced metrics.

Here's a `README.md` file for your Python project:

---

# Movie Audience Score Prediction

This project is focused on predicting movie audience ratings using various data preprocessing techniques, machine learning models, and feature extraction methods.

## Overview

This notebook processes and analyzes a dataset containing movie ratings and associated features, then applies multiple Machine-Learning techniques for prediction. The primary goal is to predict the `audience_rating` based on features such as `movie_info`, `genre`, `studio_name`, and other relevant columns.

## Features and Techniques Used:
- **Data Exploration**: Visualizing missing values, distributions, and correlations using Matplotlib and Seaborn.
- **Feature Engineering**: 
    - Text data preprocessing using **BERT embeddings** for the `movie_info` and `cast` columns.
    - **Target encoding** for high-cardinality categorical columns such as `directors` and `writers`.
    - **One-hot encoding** for categorical variables like `genre` and `studio_name`.
    - **Normalization** and **standardization** of numerical features.
- **Data Imputation**: Handling missing data by filling with median or most frequent values.
- **Exploratory Data Analysis (EDA)**: Visualizations like boxplots, scatter plots, and histograms to understand the data.
- **Statistical Tests**: Normality tests like Shapiro-Wilk and D’Agostino-Pearson to check data distributions.

## Installation and Requirements

The required libraries for this project are:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn transformers torch statsmodels
```

## Dataset

The dataset used for this project is the **Rotten Tomatoes Movies** dataset (`Rotten_Tomatoes_Movies3.xls`), which contains movie ratings, audience ratings, genre, and other features.

## Data Preprocessing

1. **Missing Values**: 
    - Dropped rows with missing `genre`, `directors`, `writers`, `cast`, and `audience_rating` values.
    - Imputed missing values in numerical columns using the median and filled missing values in categorical columns using the most frequent value.
  
2. **Date Conversion**:
    - Converted date columns (`in_theaters_date`, `on_streaming_date`) to the year.

3. **Text Embedding**:
    - Used **BERT embeddings** to represent textual data (`movie_info`, `cast`) as vector embeddings, replacing the original text columns.

4. **Encoding**:
    - Applied **Target Encoding** for `writers` and `directors` columns.
    - **One-hot encoding** for `genre` and `studio_name` columns.
    - **Ordinal encoding** for `rating` and `tomatometer_status`.

5. **Feature Scaling**:
    - Standardized numerical features (excluding `audience_rating`).

## Model Training and Evaluation

This notebook prepares the data for training but does not include model training steps in the provided code. However, the preprocessed data is ready for feeding into machine learning models such as **Random Forest**, **XGBoost**, or **Neural Networks**.

## Normality Testing

The following tests were performed to check the normality of data:
- **Shapiro-Wilk Test**
- **D’Agostino-Pearson Test**

These tests help decide whether normalization or standardization should be applied to features.

## Visualizations

Several visualizations have been included to help explore the data:
- Missing values heatmap
- Distribution of audience ratings
- Boxplots for numerical features
- Scatter plots to explore relationships between features like `tomatometer_rating` and `audience_rating`.

## Code Structure

1. **Data Loading**: 
    - Reads the Excel file into a DataFrame using `pandas`.
  
2. **Data Exploration**:
    - Displays dataset info, missing values, and descriptive statistics.
    - Visualizes missing data and distributions.
  
3. **Preprocessing**:
    - Handles missing values, feature scaling, encoding, and text embeddings.

4. **Feature Engineering**:
    - Applies BERT embeddings to text columns (`movie_info`, `cast`).
    - Performs target encoding and one-hot encoding on categorical columns.
  
5. **Final Processed Data**:
    - The processed DataFrame `df_processed` is ready for machine learning models.

## Example Usage

```python
# Load the dataset
file_path = '/kaggle/input/movie-audience-score/Rotten_Tomatoes_Movies3.xls'
df = pd.read_excel(file_path)

# Preprocess the data
df_processed = preprocess_data(df)

# Check the processed data
df_processed.head()
```

## Contributions

Feel free to fork this project, make improvements, and submit pull requests.

## License

This project is licensed under the MIT License.

