# Football Player Market Value Analysis

Final Year Dissertation Project · DkIT

An interactive dashboard analysing the factors that drive football player market value across the Big 5 European leagues (2020–2025), built entirely in Python.

## Features

| Page | Description |
|---|---|
| Overview | Dataset summary, market value distributions by league and position |
| League Comparison | Side-by-side stats, market value distributions, scatter plots per league |
| Position Comparison | Radar charts, defensive stats, age vs value by position |
| Season Trends | Year-on-year market value changes and statistical trends (2020–2025) |
| Player Profile | Search any player: photo, career stats, trend chart, and find similar players |

---

## Methodology

Three regression models fitted and compared, all built from scratch using NumPy only (no scikit-learn):

- **OLS Linear Regression**, closed-form normal equations
- **Ridge Regression**, L2-penalised regression (α=10)
- **Random Forest**, 50 CART trees with bootstrap sampling and variance reduction splits

Models run across: overall, per-league (×5), per-position (×4), per-season per-league (×25).

The **"Find Similar Players"** feature uses cosine similarity on a normalised performance feature vector.

---

## Project Structure

```
├── data/
│   ├── processed/
│   │   ├── app_data.csv               ← App dataset (enriched + image URLs)
│   │   └── player_db_enriched.csv     ← Full analysis dataset
│   └── raw/
│       ├── defensivestats/
│       ├── gkstats/
│       └── player_scores/
├── notebooks/
│   └── market_value_prediction.ipynb  ← Full analysis notebook (45 cells)
├── outputs/model_results/             ← Saved visualisation PNGs
├── streamlit_app/
│   ├── app.py                         ← Streamlit dashboard (5 pages)
│   └── requirements.txt
├── .streamlit/config.toml             ← Dark theme
└── README.md
```
