# Predicting-Song-Popularity
A comprehensive data science project analyzing Billboard Hot 100 data from 1946-2022 to predict song popularity and examine temporal trends in music features. This study employs two complementary approaches: linear regression for popularity prediction and time series analysis for trend forecasting.
Research Questions

Which sound features best predict a song's popularity today?
How have the sound features of popular songs changed across different decades?

Technical Stack

Language: R, RMarkdown
Core Libraries:

Data Analysis: tidyverse, caret
Visualization: ggplot2
Time Series: forecast, tseries, zoo


Methods: Stepwise Linear Regression, ARIMA Modeling, Cross-validation
Data Processing: Feature engineering, outlier analysis, train-test splitting

Dataset

Source: Kaggle "Billboard Hot 100 Songs Spotify Data (1946-2022)"
Size: 6,879 songs, 24 variables
Outcome Variable: Popularity (Spotify popularity score 0-100)
Key Predictors: Acousticness, Danceability, Energy, Instrumentalness, Liveness, Loudness, Speechiness, Tempo, Valence

Project Structure
music-popularity-analysis/
│
├── README.md
├── analysis/
│   ├── milestone2_JasonKenney_JoonhyunHeo.Rmd    # Main analysis file
│   └── milestone2_JasonKenney_JoonhyunHeo.pdf    # Compiled report
├── data/
│   └── Billboard_Hot100_Songs_Spotify_1946-2022.csv
├── docs/
│   └── project_requirements.pdf
└── visualizations/
    ├── popularity_distribution.png
    ├── features_timeseries.png
    ├── arima_forecast.png
    └── model_comparison.png
Key Findings
Model 1: Linear Regression (Stepwise)

Selected Features: 7 out of 9 features (excluded Tempo and Speechiness)
Performance Metrics:

RMSE: 18.00
R²: 0.25 (25% variance explained)
MAE: 14.08


Key Predictors (in order of importance):

Danceability (+): Higher danceability increases popularity
Loudness (+): Louder songs tend to be more popular
Acousticness (-): More acoustic songs are less popular on Spotify



Model 2: Time Series Analysis (ARIMA)

Features Analyzed: Danceability, Acousticness, Loudness (1946-2022)
Model Performance: ARIMA models outperformed simple mean forecasts
Historical Trends:

Danceability: Steady increase since 1980s
Acousticness: Dramatic decline starting around 1980
Loudness: Consistent increase over decades, now stabilizing


Future Forecasts (2023-2027): Trends expected to continue with some stabilization

Cross-Model Insights
A remarkable finding emerged when comparing both models: features that predict higher popularity today (danceability ↑, loudness ↑, acousticness ↓) are the same features that have been trending upward/downward historically. This suggests a co-evolution between music production techniques and listener preferences.
Business Applications

Music Production: Guidance for artists and producers on popularity-driving features
Streaming Platforms: Understanding user preferences for recommendation algorithms
Market Research: Quantifying music industry trends for strategic planning
A&R Decisions: Data-driven insights for talent scouting and song selection

Technical Achievements

Large-scale Data Analysis: Processed 6,879 observations across 76-year timespan
Model Validation: 10-fold cross-validation for robust statistical inference
Time Series Modeling: ARIMA forecasting with train-test validation (2013-2022)
Feature Engineering: Decade grouping and audio feature standardization
Reproducible Research: Complete R workflow with version control and documentation

Key Visualizations

Popularity Distribution: Histogram showing Spotify popularity scores distribution
Time Series Trends: Multi-panel plot showing evolution of key audio features
ARIMA Forecasts: Model predictions vs actual values with confidence intervals
Model Comparison: Side-by-side performance metrics and insights

Limitations & Future Work

Data Scope: Limited to Billboard Hot 100 (US commercial success bias)
Feature Aggregation: Yearly averaging may mask within-year genre variations
Popularity Metric: Spotify bias toward recent music and specific demographics
Model Complexity: Linear assumptions may not capture non-linear relationships

Proposed Extensions

Genre-specific trend analysis
Artist-level evolution studies
International market comparisons
Advanced ML models (Random Forest, XGBoost)
Lyrical sentiment analysis integration

How to Run
r# Install required packages
install.packages(c("tidyverse", "knitr", "caret", "ggplot2", 
                   "forecast", "tseries", "zoo"))

# Set working directory to project folder
setwd("path/to/music-popularity-analysis")

# Run main analysis
rmarkdown::render("analysis/milestone2_JasonKenney_JoonhyunHeo.Rmd")
Results Summary
This project successfully demonstrated that:

Predictive modeling can identify key drivers of song popularity with moderate accuracy (R² = 0.25)
Time series analysis reveals clear evolutionary patterns in music production
Cross-validation between approaches strengthens confidence in findings
Future forecasting provides actionable insights for music industry stakeholders

The convergence of popularity predictors and historical trends suggests that the music industry has evolved toward producing songs with characteristics that maximize listener engagement on modern platforms.
