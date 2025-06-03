# 🏆 PUBG Game Winner Prediction 

Overview

This project focuses on predicting the winning placement percentage (`winPlacePerc`) of players in PlayerUnknown's Battlegrounds (PUBG) matches. By leveraging various in-game statistical data, we build and evaluate several machine learning models to identify key factors contributing to a player's success and predict their final placement.

## 📌 Project Highlights

- Data exploration and cleaning of PUBG match data
- Feature selection and preprocessing
- Model training with Random Forest, XGBoost, and more
- Evaluation using accuracy, confusion matrix, and classification report
- Final predictions based on player stats

## Dataset

The dataset used for this project (`pubg.csv`) contains anonymized player statistics from PUBG matches. Each row represents a player's performance in a single match and includes features such as:

* `kills`: Number of kills.
* `damageDealt`: Total damage dealt.
* `walkDistance`: Distance walked.
* `rideDistance`: Distance driven.
* `swimDistance`: Distance swum.
* `assists`: Number of assists.
* `boosts`: Number of boost items used.
* `heals`: Number of heal items used.
* `weaponsAcquired`: Number of weapons picked up.
* `matchType`: Type of match (e.g., solo, duo, squad).
* `winPlacePerc`: The target variable, representing the player's winning placement percentage (0.0 means last, 1.0 means first).

## Project Structure

* `GameWinnerPred.ipynb`: The main Jupyter Notebook containing the complete workflow from data loading and preprocessing to model training, evaluation, and saving.
* `pubg.csv`: The raw dataset used for this project.

## Key Steps & Methodology

1.  **Data Loading and Initial Inspection**: Loading the `pubg.csv` dataset and performing initial checks.
2.  **Data Preprocessing**:
    * Handling missing values (filling numeric NaNs with the median).
    * Removing duplicate entries.
    * Dropping unnecessary columns (`Id`, `groupId`, `matchId`).
    * Encoding categorical features (`matchType` using Label Encoding).
3.  **Exploratory Data Analysis (EDA)**:
    * Visualizing feature correlations using a heatmap.
    * Analyzing the distribution of key metrics like `kills`.
4.  **Feature Engineering**:
    * Creating new features like `kill_per_distance` and `efficiency_score` to capture more nuanced player behavior.
5.  **Model Training and Evaluation**:
    * Splitting data into training and testing sets.
    * Scaling features using `StandardScaler`.
    * Training and evaluating the following regression models:
        * Linear Regression
        * Random Forest Regressor
        * Gradient Boosting Regressor
        * XGBoost Regressor
    * Evaluating models using Mean Squared Error (MSE) and R2 Score.
6.  **Model Comparison**: Presenting a comparison of all trained models based on their performance metrics.
7.  **Feature Importance Analysis**: Identifying the most influential features for predicting `winPlacePerc` using the best-performing model (XGBoost).
8.  **Model Saving**: Saving the best-performing model (`pubg_win_predictor.pkl`) for future use.

## Installation and Setup

To run this project locally, you'll need Python and the following libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost joblib
