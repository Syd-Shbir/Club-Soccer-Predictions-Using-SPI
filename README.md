# Club-Soccer-Predictions-Using-SPI

## Project Overview
This project focuses on predicting the future performance and rankings of football teams using historical Soccer Power Index (SPI) data. SPI is a comprehensive metric that evaluates a team's offensive and defensive capabilities. The analysis aims to identify trends, compare leagues, and provide accurate rank predictions for top teams. The ultimate goal is to offer insights that assist stakeholders, such as managers, analysts, and league organizers, in strategic decision-making.

## Key Features
- Analysis of SPI trends over time for top and mid-ranked teams.
- Comparison of different leagues based on SPI values and team attributes.
- Prediction of team rankings for the year 2029 using advanced modeling techniques.
- Insights into team dynamics through offensive and defensive indices.
- Visual representation of team rankings, trends, and league comparisons.

## Dataset
The dataset used in this project is derived from [FiveThirtyEight's SPI data](https://github.com/fivethirtyeight/data/tree/master/soccer-spi). Key features include:
- **Match details**: Season, date, teams, and league information.
- **Performance metrics**: SPI values, offensive and defensive ratings, and expected goals scored/conceded.
- **Probabilities**: Win, loss, and draw probabilities for each match.
- **Additional metrics**: Projected scores, adjusted scores, and match importance.

### Key Columns
```plaintext
['season', 'date', 'league_id', 'league', 'team1', 'team2', 'spi1', 'spi2',
 'prob1', 'prob2', 'probtie', 'proj_score1', 'proj_score2', 'importance1', 
 'importance2', 'score1', 'score2', 'xg1', 'xg2', 'nsxg1', 'nsxg2', 
 'adj_score1', 'adj_score2']
```

## Methods and Tools
### Data Preparation
- **Data Cleaning**: The dataset was filtered to remove missing or inconsistent values, focusing on key columns such as `team1`, `date`, and `spi1`.
- **Selection of Top 30 Teams**: Average SPI1 scores were calculated, and the top 30 teams were selected for focused analysis on competitive teams.
- **Time Series Formatting**: Data was structured into a time series format with SPI values averaged by date for consistency.
- **Feature Engineering**: Offensive and defensive indices were created by aggregating goals scored and conceded. The defensive index was standardized and negated to align higher values with better performance.

### Modeling
- **Rank Prediction**: Rankings for the top 30 teams were predicted for 2029 using two models:
  - **Random Forest Regressor**: Trained on historical SPI data to predict future values.
  - **ARIMA**: Forecasted SPI values using the `auto_arima` function to tune parameters for optimal performance.

### Evaluation
- **Metrics**:
  - Root Mean Square Error (RMSE)
  - Mean Absolute Error (MAE)
- **Visualizations**:
  - Heatmaps to visualize predicted rank changes over time.
  - Scatter plots comparing offense and defense indices for insights into team strengths.

## Results
The analysis provides:
1. Stable SPI trends for consistently high-ranking teams and fluctuations for others.
2. Insights into league comparisons, showing balanced attributes in stronger leagues.
3. Accurate predictions of team rankings for the year 2029.

## Installation
To replicate the project:
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/football-performance-prediction.git
   ```
