# trading-model
I'm building a machine learning trading model from scratch using SPY market data, feature engineering, and signal generation. This repository documents the full process!

>> Follow along with me at tiktok.com/@lera_byte

More updates coming as the model develops.

## Progress

### Part 2 — Data Pipeline
- Pulled historical SPY market data using Python (`yfinance`)
- Structured dataset with date, open, high, low, close, and volume
- Built a repeatable data pipeline

### Part 3 — System Scaffolding
- Defined the high-level model pipeline
- Designed how inputs → model → outputs will work
- Focused on methodology before implementation

### Part 4 — Feature Engineering
- Transformed raw price data into structured signals
- Built features capturing:
  - momentum (multi-period returns)
  - trend (moving-average gaps)
  - volatility (rolling standard deviation)
  - trading activity (volume z-score)
  - market regime and range positioning
- Created a multi-dimensional representation of market behavior

### Part 5 — Signal Definition
- Defined what counts as a meaningful market move
- Switched from predicting every move to filtering for significant ones
- Used a 3-day forward return with a threshold to separate signal from noise
- Framed the problem as identifying setups that actually matter

### Part 6 — Model Training
- Split data into chronological train, validation, and test sets
- Trained a `HistGradientBoostingClassifier` on engineered features
- Used an iterative learning approach where the model improves by correcting errors
- Calibrated model probabilities using isotonic regression to produce usable confidence scores

---

## Current Status

At this stage, the system:
- Has a fully defined data pipeline
- Uses engineered features to describe market behavior
- Has a trained model capable of producing probability-based predictions

The model is not yet deployed or fully integrated into a trading workflow.

---

## Coming Next

- Signal filtering and confidence thresholds  
- Evaluating prediction quality vs trade quality  
- Converting model output into actionable signals  
- Backtesting the system  
- Connecting the model to a paper trading environment (Thinkorswim)  

---

## Repository Structure (current)
