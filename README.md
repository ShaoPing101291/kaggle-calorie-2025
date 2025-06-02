# kaggle-calorie-2025
Ranked in the top 6% among 9,345 entrants and 37,000+ submissions in a highly competitive Kaggle challenge.

# Predict Calorie Expenditure

This project is part of the 2025 Kaggle Playground Series. The goal is to predict how many calories were burned during a workout. It’s a great chance to practice machine learning with a fun and beginner-friendly dataset.

##  Motivation

At the beginning of 2025, I started learning Python web scraping. In April, I joined Darren's ML course and started exploring machine learning. I used this competition to apply what I’ve learned and to improve my skills.

##  Dataset

- Source: [Kaggle - Predict Calorie Expenditure](https://www.kaggle.com/competitions/playground-series-s5e5/overview)
- Format: CSV
- Features provided:
  - `id`, `Sex`, `Age`, `Height`, `Weight`, `Duration`, `Heart_Rate`, `Body_Temp`, `Calories`
- Additional features I created:
  - `BMI`, `Temp_Level`, `HRxTime`

There were no missing values in the dataset. I used the IQR method to handle outliers.

##  Methods

- Tried different models at the beginning: Linear Regression, KNN, Logistic Regression, CatBoost, XGBoost, LightGBM
- Feature engineering:
  - I created two new features: `Temp_Level` and `HRxTime`
  - I also applied **Target Encoding (TE)** to the `Sex`,`Age_Group`, `Temp_Level`, `Intensity` column to improve model performance
- Final solution:
  - Base models: CatBoost + XGBoost
  - Final stacking: LightGBM + Ridge
- Feature selection:
  - After testing many features, I kept 10 final ones

- Evaluation Metric: RMSLE

## Results

- Public Leaderboard: **0.05677** (Rank: **411**)
- Private Leaderboard: **0.05875** (Rank: **590**)

##  What I Learned

- I overused the IQR method to fit the public leaderboard, which caused overfitting and worse results on private.
- Feature selection and outlier handling are very important for improving scores.
- Next time, I will handle outliers more objectively, not just based on public score performance.

##  Project Structure

```
predict-calorie-expenditure/
│
├── README.md                 # Project description
├── requirements.txt          # Python packages used
│
├── notebooks/
│   ├── 1_data_preprocessing.ipynb   # Data cleaning and feature engineering
│   └── 2_model_training.ipynb       # Model training, blending, and prediction
│
└── output/
    └── final_submission.csv         # Final submission file 
```

##  How to Run

1. Clone this repo  
2. Install requirements:  
   ```
   !pip install -r requirements.txt
   ```
3. Run notebooks in the `notebooks/` folder in order

##  References

- [Kaggle Competition Page](https://www.kaggle.com/competitions/playground-series-s5e5/overview)
- [telunyang](https://github.com/telunyang/python_machine_learning)
