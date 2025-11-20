CryPe 2.0 — AI-Powered Crypto Price Prediction Engine

CryPe 2.0 is a multi-modal crypto forecasting system that combines technical indicators, news sentiment, and machine learning models (XGBoost + LSTM) to predict short-term crypto price direction and returns.

This project builds the foundation for CryPe 3.0 — a fully multimodal, deep-learning-driven market prediction ecosystem.

🧠 Project Overview

CryPe 2.0 transforms raw news + price data into a highly engineered dataset and trains two prediction models:

✔ XGBoost Classifier

Predicts next-day direction (up/down)

✔ LSTM Time-Series Model

Predicts next-day return value

✔ Hybrid Ensemble

Combines both models for smoothed final predictions

Accuracy is intentionally not the main focus here — the goal is a complete, production-style ML pipeline, ready for future upgrades.

📊 Features
🔎 1. Sentiment Processing

Extracted tickers from news headlines + full text

Calculated:

avg_sentiment

positive_ratio

negative_ratio

news_count per day

Continuity handling (FFILL missing days)

Advanced sentiment features:

Lag features (1, 3, 7 days)

Rolling averages

Sentiment volatility

Sentiment shocks

Rolling news count

📈 2. Technical Indicators

For each crypto ticker:

SMA: 7, 20, 50

EMA: 20

RSI: 14

MACD, Signal, Histogram

Bollinger Bands: Middle, Upper, Lower, Width, Std

OBV (On-Balance Volume)

ATR (Volatility)

ROC (Rate of Change)

Price spreads: HL, HC, LC

Returns, 3-day returns

🧩 3. Machine Learning Models
🔥 XGBoost Classifier

Predicts if next-day return > 0
Performance (baseline):

Accuracy: ~0.54

🔥 LSTM Time-Series Model

Input shape: (60 timesteps × feature_window)
Predicts: next-day return

Performance:

MSE ≈ 0.005–0.007

MAE ≈ 0.048–0.058

Directional accuracy ≈ 0.49–0.50

🔥 Ensemble

Final prediction = average of XGBoost + LSTM outputs

📁 Dataset Structure

Total samples: ~11,600

Assets: 15 major crypto tickers

Features: 40+ engineered features

Targets:

direction (binary)

target (next-day return)

target_3d (3-day return %)

🛠 Tech Stack

Python

Pandas, NumPy

Scikit-learn

XGBoost

TensorFlow / Keras

Ta-Lib / pandas-ta

Yahoo Finance API

Flair Sentiment Model
