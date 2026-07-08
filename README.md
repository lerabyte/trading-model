# Automated Trading Model

I'm building a machine learning trading model from scratch using SPY market data, feature engineering, signal generation, backtesting, and paper-trading preparation. This repository documents the full 10-part process from raw market data to a completed model pipeline.

Follow along with me on TikTok: [@lera_byte](https://www.tiktok.com/@lerabyte/video/7626178088182828319)

## Overview

This project is an end-to-end machine learning trading model built on historical SPY market data.

The goal of the project is not to predict every tiny market move. Instead, the system focuses on identifying higher-quality market setups by combining engineered features, meaningful signal definitions, model-based probability predictions, confidence filtering, and backtesting.

The final pipeline takes historical price and volume data, creates market behavior features, trains a machine learning classifier, generates probability-based signals, evaluates those signals through backtesting, and prepares the model for a paper-trading workflow.

## Final Project Status

The model pipeline is complete through the first full version.

The finished system includes:

- Historical SPY data collection
- Repeatable data preprocessing
- Feature engineering
- Forward-looking signal definition
- Chronological train, validation, and test splits
- Machine learning model training
- Probability calibration
- Confidence-based signal filtering
- Backtesting logic
- Paper-trading preparation

This project is still educational and experimental, but the full first version of the model workflow has been built.

## Repository Structure

```text
trading-model/
├── README.md
├── LICENSE
├── .gitignore
├── requirements.txt
└── histGradientBoost/
    └── model training and signal generation files
````

## Tech Stack

* Python
* pandas
* NumPy
* yfinance
* scikit-learn
* HistGradientBoostingClassifier
* Probability calibration
* Time-series-aware validation
* Backtesting logic
* Signal filtering

## Methodology

The project follows a full machine learning workflow designed specifically for financial time series data.

Instead of randomly splitting the data, the model uses chronological splits to better reflect how trading models are actually tested. The model is trained on earlier data, validated on later data, and tested on unseen future periods.

The prediction target is based on forward returns, meaning the model learns to identify conditions that may lead to a meaningful move over the next few trading days.

## Progress

### Part 1 — Project Setup

* Defined the goal of building a machine learning trading model from scratch
* Chose SPY as the main asset for the first version
* Set up the repository structure
* Planned the full modeling pipeline from data to signal generation

### Part 2 — Data Pipeline

* Pulled historical SPY market data using Python and `yfinance`
* Structured the dataset with date, open, high, low, close, and volume
* Built a repeatable data pipeline that can be reused as the model develops

### Part 3 — System Scaffolding

* Defined the high-level model pipeline
* Designed how inputs, features, model predictions, and outputs connect
* Focused on methodology before implementation
* Created the foundation for a complete signal-generation workflow

### Part 4 — Feature Engineering

* Transformed raw price data into structured market signals
* Built features capturing:

  * momentum using multi-period returns
  * trend using moving-average gaps
  * volatility using rolling standard deviation
  * trading activity using volume z-scores
  * market regime and range positioning
* Created a multi-dimensional representation of market behavior

### Part 5 — Signal Definition

* Defined what counts as a meaningful market move
* Switched from predicting every small move to filtering for significant ones
* Used a 3-day forward return with a threshold to separate signal from noise
* Framed the problem as identifying setups that actually matter

### Part 6 — Model Training

* Split data into chronological train, validation, and test sets
* Trained a `HistGradientBoostingClassifier` on engineered features
* Used a model that can capture nonlinear patterns in the data
* Generated probability-based predictions instead of only simple class labels

### Part 7 — Probability Calibration

* Calibrated model probabilities using isotonic regression
* Improved the usefulness of confidence scores
* Prepared the model outputs for threshold-based signal filtering
* Made the predictions easier to interpret as probability estimates

### Part 8 — Signal Filtering

* Converted raw model probabilities into filtered trading signals
* Used confidence thresholds to avoid low-quality predictions
* Focused on fewer, higher-conviction setups instead of forcing a prediction every day
* Created the first version of the model's signal-generation rules

### Part 9 — Backtesting

* Built a basic backtesting workflow to evaluate model-generated signals
* Compared model predictions against forward returns
* Evaluated whether prediction quality translated into useful trade quality
* Reviewed signal frequency, direction, and outcome behavior

### Part 10 — Paper-Trading Preparation

* Prepared the model logic for a paper-trading workflow
* Organized the output so model predictions can be reviewed as potential trade signals
* Created a completed first version of the system from raw data to model-generated signals
* Identified future improvements for live testing, risk controls, and more advanced evaluation

## How to Run

Install the required packages:

```bash
pip install -r requirements.txt
```

Then run the training script inside the `histGradientBoost` folder:

```bash
cd histGradientBoost
python train_model.py
```

Depending on the local setup, the script may pull SPY data directly using `yfinance` or use saved data files if they have already been generated.

## What I Learned

Through this project, I learned how machine learning models can be applied to financial time series data and why trading models require a different workflow than normal supervised learning projects.

Some of the biggest lessons were:

* Financial data must be split chronologically, not randomly
* Raw price data needs to be transformed into useful features
* Predicting every market move creates too much noise
* Confidence thresholds can be more useful than raw predictions
* A model can have decent prediction accuracy but still need backtesting to evaluate trade quality
* Backtesting and risk controls are just as important as model training

## Limitations

This is the first completed version of the project, so there are still limitations:

* The model is trained on historical SPY data only
* The backtesting logic is basic
* Transaction costs, slippage, and position sizing may need more advanced modeling
* The system has not been used for real trading
* The model may not generalize to different market regimes without further testing

Disclaimer: This project is for educational and research purposes only. It is not financial advice, investment advice, or a recommendation to buy or sell any security. The model is experimental and should not be used for real trading without extensive validation, risk controls, and out-of-sample testing.

```
```

