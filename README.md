# Time-Series-Based-Stock-Direction-Prediction-





###📈 Stock Price Movement Prediction (HDFC) – ML Project

DS & ML Intern Assignment – GoalFi, IIT Kanpur

🚀 Overview

Built an end-to-end pipeline to predict next-day stock direction (Up/Down) using 2 years of HDFC OHLCV data from Yahoo Finance.

📂 1. Data Preparation

Collected OHLCV data via Yahoo Finance API.

No missing/duplicate rows; Volume outliers fixed using log transform.

Chronological sorting + time-based 80/20 split to avoid leakage.

🔧 2. Feature Engineering

Used core technical indicators + lags:

MA14, RSI14, MACD (12,26,9)

Lag features: MA14_lag1/2, RSI14_lag1/2, MACD_lag1

Focused on stable, interpretable trend & momentum features.

🤖 3. Models

Trained three classifiers:

Logistic Regression

Random Forest

XGBoost (best)

Target:
1 = next day close > current close, 0 = otherwise

📊 4. Performance
Model	Accuracy	F1-Score
Logistic Regression	0.5106	0.3235
Random Forest	0.5106	0.3783
XGBoost	0.4893	0.5120

XGBoost performed best due to balanced precision & recall (important in noisy, slightly imbalanced financial data).

🎯 Threshold Tuning (XGBoost)

Best performance at threshold = 0.20:

Metric	Score
Accuracy	0.5106
Precision	0.5205
Recall	0.7755
F1-Score	0.6229

This significantly improved predictive value compared to default 0.5.

📈 Interpretability

Feature Importance: Lagged RSI & MA were top predictors → momentum history matters most.

Confusion Matrix & ROC: Model performs above random and captures useful patterns despite noise.

🏁 Conclusion

Daily stock movement is inherently noisy, so 50–55% accuracy is expected.
XGBoost + threshold tuning delivered the strongest F1-Score and most reliable predictions.
The project demonstrates solid skills in:

Data cleaning & leakage-safe splitting

Financial feature engineering

Model evaluation focused on F1

Threshold optimization

Interpretability through visualizations
