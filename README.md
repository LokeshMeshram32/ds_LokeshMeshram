# 📊 Data Science Assignment – Lokesh Meshram

## 📁 Folder Structure
ds_LokeshMeshram/
│
├── Notebook1.ipynb
├── ds_report.pdf
├── README.md
├── csv_files/
│ ├── market_sentiment.csv
│ ├── trader_data.csv
│ └── any_other_dataset.csv
├── outputs/
│ ├── daily_correlation_plot.png
│ ├── lagged_corr_heatmap.png
│ └── top_accounts_analysis.png
└── requirements.txt

yaml
Copy code

---

## 🧠 Project Overview
This project analyzes **the relationship between market sentiment and trading activity** using two key datasets:

1. **Market Sentiment Data** – Daily index values that measure the level of investor emotion from “Extreme Fear” to “Extreme Greed”.
2. **Trader Data** – Transaction-level records with timestamps, trade sizes, leverage, and profit/loss information.

**Objective:**  
To explore whether investor sentiment has a measurable effect on trading behavior — including trade count, total volume, and profit/loss patterns — using statistical and exploratory data analysis.

---

## 🚀 Google Colab Notebook
You can run or review the full analysis interactively here:

👉 **[Open in Google Colab](https://colab.research.google.com/drive/<YOUR_COLAB_NOTEBOOK_ID>)**

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
Install dependencies using the provided requirements file:

```bash
pip install -r requirements.txt
Minimal environment versions:

Package	Version
pandas	>= 2.2.0
numpy	>= 1.26.0
matplotlib	>= 3.8.0
seaborn	>= 0.13.0
scipy	>= 1.11.0
scikit-learn	>= 1.3.0

🧩 How to Run Locally
Clone or unzip this folder:

bash
Copy code
unzip ds_LokeshMeshram.zip
cd ds_LokeshMeshram
Open Notebook1.ipynb in Jupyter Notebook or upload to Google Colab.

Run all cells sequentially from top to bottom.

Check generated results in:

/csv_files → intermediate cleaned datasets

/outputs → generated charts and summary plots

🧠 Summary of Findings
Aspect	Observation
Correlation Strength	Weak negative (−0.22 Pearson, −0.18 Spearman)
Time-Lag Effect	Peak lag correlation around −2 days
Account Patterns	High-leverage traders show inverse sentiment response
Statistical Significance	Most correlations not significant at 95% confidence
Recommendation	Combine sentiment with volatility and returns for predictive modeling

⚖️ Limitations
Some missing trade timestamps may cause slight day-boundary mismatches.

Sentiment values interpolated — may reduce variability.

Correlation analysis does not imply causation.

Market sentiment index lacks direct price/volatility integration.

🔮 Future Improvements
Integrate price volatility and return metrics with sentiment.

Apply Granger causality tests for directional influence.

Extend analysis to hourly windows for higher granularity.

Cluster accounts using behavioral metrics (PnL variance, leverage usage).

Experiment with machine learning models (Random Forest, XGBoost) for predictive insights.

👨‍💻 Author Information
Author: Lokesh Meshram
Course: Data Science & Analytics
Instructor: Prof. S. S. Chiwande
Institute: PCCOE
Submission Date: October 2025

