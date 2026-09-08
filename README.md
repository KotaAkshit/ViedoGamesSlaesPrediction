🎮 Video Game Sales Prediction

A machine learning project that predicts the global sales of video games (in millions of units) using information such as platform, genre, release year, critic scores, user scores, and rating.

The project performs exploratory data analysis, data preprocessing, feature engineering, model training, hyperparameter tuning, evaluation, and finally uses XGBoost to predict sales for a new video game.

📌 Project Overview

The goal of this project is to build regression models that can estimate the global sales of a video game based on its available attributes.

Problem Type

Machine Learning: Supervised Learning

Task: Regression

Target: Global_Sales

Best/Final Model Used for Prediction: XGBoost Regressor

📂 Project Structure

VideoGamesSalesPrediction-main/
│
├── Video_Game_Sales_Prediction.ipynb   # Complete ML notebook
├── video-game-sales.csv                # Original dataset
└── README.md                           # Project documentation

📊 Dataset

The dataset contains video game information including:

Name

Platform

Year of Release

Genre

Publisher

Developer

Critic Score

Critic Count

User Score

User Count

Rating

Regional sales

Global sales

The project focuses on selected platforms including:

PS2, PS3, PS4, X360, XOne, Wii, WiiU, and PC.

🔄 Machine Learning Workflow

Dataset
   ↓
Exploratory Data Analysis
   ↓
Data Cleaning
   ↓
Missing Value Handling
   ↓
Feature Selection
   ↓
Categorical Encoding
   ↓
Feature Engineering
   ↓
Feature Scaling
   ↓
Log Transformation of Target
   ↓
Train-Test Split
   ↓
Model Training
   ↓
Model Evaluation
   ↓
Model Comparison
   ↓
XGBoost Prediction

🧹 Data Preprocessing

The following preprocessing steps are performed:

Load the dataset using Pandas.

Filter the dataset to selected gaming platforms.

Analyze missing values.

Remove records with missing Critic_Count.

Fill missing values using appropriate statistical methods:

Mean for User_Count

Median for Year_of_Release

Mode for Rating, Developer, and Publisher

Convert User_Score from text to numeric.

Treat tbd user scores as missing values and fill them with the median.

Remove features that are not used for prediction, including regional sales fields.

Label-encode categorical features:

Platform

Genre

Rating

Convert Year_of_Release into Game_Age.

Standardize numerical features using StandardScaler.

Apply log1p transformation to Global_Sales to reduce skewness.

🤖 Models Used

The project compares multiple regression algorithms:

1. K-Nearest Neighbors (KNN) Regressor

Different values of K are evaluated using 5-fold cross-validation to select the optimal number of neighbors.

2. Linear Regression

A baseline regression model used to understand the linear relationship between the features and global sales.

3. Support Vector Regressor (SVR)

GridSearchCV is used to tune parameters such as:

C

gamma

kernel

4. Random Forest Regressor

Hyperparameter tuning is performed for:

n_estimators

max_depth

min_samples_split

Feature importance is also analyzed using the trained Random Forest model.

5. XGBoost Regressor

XGBoost is used as the final prediction model with parameters including:

n_estimators = 100

learning_rate = 0.1

max_depth = 5

subsample = 0.8

colsample_bytree = 0.8

📈 Evaluation Metrics

The models are evaluated using:

R² Score

Measures how well the model explains the variation in the target variable.

Higher R² generally indicates better predictive performance.

RMSE

Root Mean Squared Error measures the average magnitude of prediction errors.

Lower RMSE indicates better performance.

🎯 Prediction for New Games

The notebook includes an interactive prediction section where users can enter:

Platform

Year of Release

Genre

Critic Score

Critic Count

User Score

User Count

Rating

The input is passed through the same encoding and scaling process used during training, and the trained XGBoost model predicts global sales in million units.

🛠️ Technologies Used

Python

Pandas

NumPy

Matplotlib

Seaborn

Scikit-learn

XGBoost

Jupyter Notebook / Google Colab

▶️ How to Run

Option 1: Google Colab

Open the .ipynb file in Google Colab.

Upload video-game-sales.csv.

Make sure the CSV path matches the path used in the notebook.

Run the notebook cells from top to bottom.

Option 2: Local Jupyter Notebook

Install the required libraries:

pip install pandas numpy matplotlib seaborn scikit-learn xgboost jupyter

Then start Jupyter:

jupyter notebook

Open:

Video_Game_Sales_Prediction.ipynb

and run the cells in order.

💡 Key Highlights

Performed complete exploratory data analysis.

Handled missing and inconsistent values.

Used label encoding for categorical variables.

Applied feature engineering using game age.

Standardized numerical features.

Reduced target-variable skewness using logarithmic transformation.

Compared five regression approaches.

Used cross-validation and GridSearchCV for model tuning.

Analyzed Random Forest feature importance.

Built an interactive prediction workflow using XGBoost.

🚀 Future Improvements

Build a web interface using Streamlit or Flask.

Save the trained model and preprocessing objects using joblib.

Use one-hot encoding or target encoding instead of label encoding where appropriate.

Add automated model selection.

Perform more extensive hyperparameter optimization.

Add additional game metadata and market-related features.

Deploy the prediction model as a web application or API.
