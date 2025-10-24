# 📊 Data Science Project – Lokesh Meshram

### Overview
This project explores how **market sentiment** influences **trading activity**.  
It combines daily sentiment data with trade-level information to see whether fear or greed in the market has any measurable impact on the number and size of trades or on profit and loss patterns.

The analysis was done entirely in Python using pandas, matplotlib, seaborn, and related libraries.  
All steps from cleaning to visualization are inside the notebook below.

---

## 🚀 Google Colab Notebook
You can run or review the full analysis interactively here:

👉 **[Open in Google Colab](https://colab.research.google.com/drive/1WLm8ao1Ebihai3GOrJ9NkIietqy5doF1?usp=sharing)**

---

## 🧹 Data Cleaning Summary
Steps performed to prepare the data for analysis:

- Converted timestamp columns (`Timestamp IST`) to timezone-aware UTC datetimes.  
- Standardized column names across datasets.  
- Forward/backward-filled missing sentiment values to maintain continuity.  
- Removed duplicate records and outliers using percentile-based clipping.  
- Created new daily-level aggregates:
  - **Total number of trades**
  - **Total trade size (USD)**
  - **Average trade size**
  - **Average and net daily PnL**
- Saved intermediate cleaned data in `/csv_files`.

---

## 📊 Analysis Conducted
1. **Descriptive Statistics**
   - Summary stats for trade size, PnL, leverage, and sentiment.
   - Distribution plots and skewness/kurtosis checks.

2. **Correlation Analysis**
   - Pearson and Spearman correlations between daily sentiment and trading metrics.
   - Included p-values for statistical significance.

3. **Lagged and Rolling Correlations**
   - Examined sentiment leading/lagging effects (−7 to +7 days).
   - Rolling 30-day correlation trend visualization.

4. **Account-Level Behavior**
   - Top accounts ranked by trade size and profit.
   - Normalized metrics (PnL per trade, leverage ratio).

5. **Event Study**
   - Focused on “Extreme Fear” and “Extreme Greed” sentiment events.
   - Compared pre/post-day trading activity.

All visualizations are exported in `/outputs`.

---

## 📈 Key Insights
- Sentiment and trading volume have a **weak negative correlation** overall.  
- Correlations vary through time — notably stronger around extreme sentiment days.  
- Lag analysis indicates that sentiment changes often precede volume shifts by 1–2 days.  
- Large-volume (“whale”) accounts show contrarian behavior — trading more heavily on fearful days.  
- Market sentiment alone is **not sufficient for prediction**, but it can complement volatility or return features.

---

## ⚙️ Technical Implementation
- Implemented in **Python 3.10+** (tested on Google Colab).  
- Libraries used: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy`, and `scikit-learn`.  
- Reproducibility ensured with a fixed random seed and consistent timezone handling.  
- Key output artifacts (plots, CSVs) stored in their respective folders for grading.

---

## 🧾 Requirements
Install dependencies using the provided requirements.txt file:

```bash
pip install -r requirements.txt
```

🧩 How to Run Locally
- Clone or unzip this folder.
- Create and activate a virtual environment.
- Install dependencies as per stated above.
- Run all cells sequentially from top to bottom.
- Check generated results in /outputs → generated charts and summary plots

🧠 Summary of Findings
- Aspect	Observation
- Correlation Strength	Weak negative (−0.22 Pearson, −0.18 Spearman)
- Time-Lag Effect	Peak lag correlation around −2 days
- Account Patterns	High-leverage traders show inverse sentiment response
- Statistical Significance	Most correlations not significant at 95% confidence
- Recommendation	Combine sentiment with volatility and returns for predictive modeling

⚖️ Limitations
- Some missing trade timestamps may cause slight day-boundary mismatches.
- Sentiment values interpolated may reduce variability.
- Correlation analysis does not imply causation.
- Market sentiment index lacks direct price/volatility integration.

🔮 Future Improvements
- Integrate price volatility and return metrics with sentiment.
- Apply Granger causality tests for directional influence.
- Extend analysis to hourly windows for higher granularity.
- Cluster accounts using behavioral metrics (PnL variance, leverage usage).
- Experiment with machine learning models (Random Forest, XGBoost) for predictive insights.

👨‍💻 Author Information
- Author: Lokesh Meshram
