# Music Over the Decades: Predicting Song Popularity

A comprehensive data science project analyzing Billboard Hot 100 data from 1946-2022 to predict song popularity and examine temporal trends in music features using linear regression and time series analysis.

## Research Questions

1. **Which sound features best predict a song's popularity today?**
2. **How have the sound features of popular songs changed across different decades?**

## Dataset

- **Source**: [Kaggle: Billboard Hot 100 Songs Spotify Data](https://www.kaggle.com/datasets/tushar5harma/billboard-hot-100-songs-spotify-data-1946-2022)
- **Size**: 6,879 songs with 24 variables
- **Timespan**: 1946-2022 (76 years)
- **Target Variable**: Popularity (0-100 Spotify score)
- **Key Features**: Acousticness, Danceability, Energy, Instrumentalness, Liveness, Loudness, Speechiness, Tempo, Valence

## Technical Stack

- **Language**: R
- **Core Libraries**: `tidyverse`, `caret`, `ggplot2`, `forecast`, `tseries`, `zoo`
- **Methods**: Stepwise Linear Regression, ARIMA Modeling, 10-fold Cross-validation

## Key Findings

### Model 1: Linear Regression (Stepwise)
- **Performance**: RMSE = 18.00, R² = 0.25, MAE = 14.08
- **Selected Features**: 7 out of 9 features (excluded Tempo and Speechiness)
- **Key Predictors**:
  - **Danceability** (+): Higher danceability increases popularity
  - **Loudness** (+): Louder songs tend to be more popular
  - **Acousticness** (-): More acoustic songs are less popular on Spotify

### Model 2: Time Series Analysis (ARIMA)
- **Features Analyzed**: Danceability, Acousticness, Loudness (1946-2022)
- **Performance**: ARIMA models outperformed simple mean forecasts
- **Historical Trends**:
  - **Danceability**: Steady increase since 1980s
  - **Acousticness**: Dramatic decline starting around 1980
  - **Loudness**: Consistent increase over decades, now stabilizing
- **Future Forecasts**: 5-year predictions (2023-2027) showing trend continuation

### Cross-Model Insights
Features that predict higher popularity today (danceability ↑, loudness ↑, acousticness ↓) are the same features that have been trending historically, suggesting co-evolution between music production and listener preferences.

## Installation and Usage

### Prerequisites
```r
install.packages(c("tidyverse", "knitr", "caret", "ggplot2", 
                   "forecast", "tseries", "zoo"))
```

### Running the Analysis
```r
# Set working directory
setwd("path/to/music-popularity-analysis")

# Run main analysis
rmarkdown::render("analysis/milestone2_JasonKenney_JoonhyunHeo.Rmd")
```

## Results Summary

This project successfully demonstrated:
1. **Predictive modeling** can identify key drivers of song popularity with moderate accuracy (R² = 0.25)
2. **Time series analysis** reveals clear evolutionary patterns in music production
3. **Cross-validation** between approaches strengthens confidence in findings
4. **Future forecasting** provides actionable insights for music industry stakeholders

## Business Applications

- **Music Production**: Guidance for artists and producers on popularity-driving features
- **Streaming Platforms**: Understanding user preferences for recommendation algorithms
- **Market Research**: Quantifying music industry trends for strategic planning
- **A&R Decisions**: Data-driven insights for talent scouting and song selection

## Limitations

- **Data Scope**: Limited to Billboard Hot 100 (US commercial success bias)
- **Feature Aggregation**: Yearly averaging may mask within-year genre variations
- **Popularity Metric**: Spotify bias toward recent music and specific demographics
- **Model Complexity**: Linear assumptions may not capture non-linear relationships

## Future Work

- Genre-specific trend analysis
- Artist-level evolution studies
- International market comparisons
- Advanced ML models (Random Forest, XGBoost)
- Lyrical sentiment analysis integration


*This project was completed as part of the Advanced Software Engineering course at UMass Amherst, demonstrating statistical modeling, data visualization, and reproducible research capabilities.*
