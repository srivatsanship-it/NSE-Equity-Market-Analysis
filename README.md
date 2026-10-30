# Where Is the Money Really Flowing? — Indian Equity Market Analysis (NSE data, October 2026)

Repository: https://github.com/srivatsanship-it/NSE-Equity-Market-Analysis

**Final project — Data Analytics using Python** · Domain: Finance (Capital Markets) · Period: 1–27 Oct 2026 (17 trading sessions)

## Business problem
A brokerage or market-analytics team needs to know *where genuine investor money is going*. Price moves alone mislead; this project combines **liquidity** (turnover, concentration) and **conviction** (delivery % — the share of traded shares actually taken into delivery) across segments, industries and stocks.

## Data (original sources — National Stock Exchange of India)
| File | What it is | Source |
|---|---|---|
| `nse_bhavcopy_raw.csv` | Full Bhavcopy with delivery data — one row per security per trading day (59,922 rows × 15 columns) | https://www.nseindia.com/all-reports |
| `nifty500_industry_raw.csv` | Official Nifty 500 list with industry (501 rows × 5 columns) | https://www.nseindia.com/static/products-services/indices-nifty500-index |

Both files are stored here **unchanged**, exactly as downloaded. Data belongs to NSE and is used for educational analysis.
*(Collected with `Collection of NSE data.ipynb` in this repository; the last three sessions of October, 28–30 Oct, were not yet published at collection time.)*

## What the notebook does
`NSE_Equity_Market_Analysis_Final_Project.ipynb` follows four stages:
1. **Problem & dataset** — objectives, business questions, data dictionary, initial EDA
2. **Cleaning & feature engineering** — hidden missing values (`-`), text-typed numbers, a placeholder company in the official list, reconciliation checks, segments, industries, returns, turnover in ₹ crore
3. **Statistics & visuals** — central tendency, variance, skewness/kurtosis, outliers, 8 hypothesis tests, 17 charts (univariate, bivariate, multivariate, deep-dive)
4. **Insights & decisions** — key insights, baseline prediction test, a conviction-screening tool, recommendations, limitations

## Headline findings
- October was a **weak, jumpy month**: 57 % of stock-days fell, only 7 of 17 sessions had more advancers than decliners, and only IT (+10.5 %) and Telecom (+3.2 %) gained.
- **Trading is concentrated and mostly intraday**: 104 stocks carry half of all turnover; delivery % falls as liquidity rises (ρ = −0.66).
- **Delivery went with selling, not buying**: higher delivery on down-days (ρ = −0.12).
- The **Nifty 500 is a different market**: 18 % of stocks, 73.5 % of turnover, lower delivery, calmer prices.
- **Delivery % alone does not predict tomorrow's move** (AUC 0.45–0.47 on unseen sessions).

## How to run
1. Open the notebook in Google Colab.
2. The notebook loads both raw CSV files directly from this repository (section 1.7). If they are ever missing, it asks you to upload them.
3. Runtime → Run all.

**Tools:** Python · Pandas · NumPy · Matplotlib · Seaborn · SciPy · scikit-learn
