# Bitcoin Market Sentiment vs Hyperliquid Trader Performance

## Overview
This project analyzes the relationship between Bitcoin market sentiment (Fear/Greed index) and trader performance using historical Hyperliquid trading data.

## Dataset Sources
1. **Hyperliquid Trader Data**  
   - Columns: account, coin, execution price, size, side, timestamp, closed PnL, leverage, etc.

2. **Fear & Greed Index**  
   - Columns: timestamp, value, classification (Fear/Greed/Extreme Fear/Extreme Greed/Neutral), date.

## Project Workflow
1. **Data Loading & Cleaning**
   - Standardized column names
   - Converted timestamps to datetime format
   - Mapped sentiment to binary form (`0` = Fear, `1` = Greed)

2. **Data Aggregation**
   - Daily-level metrics (sum PnL, mean PnL, win rate, average leverage, etc.)
   - Account-level performance metrics

3. **Exploratory Data Analysis (EDA)**
   - Daily PnL trends with sentiment overlays
   - Distribution of trade PnL by sentiment classification
   - Account-level leverage vs PnL scatterplot

4. **Statistical Testing**
   - Mann–Whitney U test to compare PnL distributions between Fear and Greed days
   - Result: Statistically significant difference (p-value < 0.00001)

5. **Predictive Modeling**
   - Random Forest model predicting next-day PnL from lagged sentiment & trading metrics
   - MAE = 62,919, R² = 0.038 (low predictive power)

## Key Findings
- PnL is significantly higher on Greed days compared to Fear days.
- Sentiment alone is a weak predictor of next-day PnL.
- Visual analysis shows notable clustering of high PnL during prolonged Greed periods.

## Folder Structure
```
csv_files/    # Aggregated datasets (daily & account level)
outputs/      # Saved visualizations (PNG format)
ds_report.pdf # Final analysis report
README.md     # Project description
```
  
## Requirements
```
pandas
matplotlib
seaborn
scikit-learn
xgboost
statsmodels
gdown
reportlab
```
Install via:
```bash
pip install pandas matplotlib seaborn scikit-learn xgboost statsmodels gdown reportlab
```

## How to Run
1. Open the notebook in Google Colab or locally.
2. Install dependencies.
3. Download the datasets using `gdown` or manually place them in the working directory.
4. Execute cells step-by-step to reproduce the analysis.

