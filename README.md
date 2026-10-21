# COVID-19 Analysis and Forecasting (Johns Hopkins CSSE Data)

Capstone project **PRCP-1023** (Healthcare domain). The project analyses the Johns Hopkins CSSE COVID-19 dataset, builds models to forecast daily new cases for **India** over a **30-day horizon**, compares the models, and gives recommendations to the health department. Everything is in a single Jupyter notebook.

## Problem Statement

1. Prepare a complete data analysis report on the given data.
2. Fix a prediction period and build a model to forecast COVID-19 cases for a specific country or region.
3. **Model comparison:** ARIMA and regression models with lag features compared against a 7-day average baseline on a held-out 30-day test window using MAE.

Plus a **Model Comparison Report** and a **Report on Challenges Faced**.

The full brief is in [`Problem Statement/`](Problem%20Statement/).

## Dataset

- Source: [JHU CSSE COVID-19 Data Repository](https://github.com/CSSEGISandData/COVID-19)
- Files used (raw, cumulative, country level):
  - `time_series_covid19_confirmed_global.csv`
  - `time_series_covid19_deaths_global.csv`
  - `time_series_covid19_recovered_global.csv`
- Period covered: 22 Jan 2020 to 21 Sep 2020

## Approach

1. **Data analysis (EDA):** trends in confirmed cases, deaths and recoveries, plus a global and country-level view.
2. **Forecasting:** daily new cases for India derived from the cumulative data, using lag features and time-series cross-validation (3 folds).
3. **Model comparison:** several models compared on a held-out 30-day test window using MAE.
4. **Recommendations:** health department suggestions based on the forecast.
5. **Challenges report:** data issues faced and the techniques used to handle them.

## Key Results

- Best model: Linear Regression (lag features)
- Test MAE: about 6,600 cases/day | MAPE: 8.2%
- 67.6% improvement over a 7-day average baseline
- 30-day India forecast averages about 109k cases/day vs about 91.6k/day over the last 7 days

See the notebook for the full comparison table and charts.

## Repository Structure

```
.
├── covid_forecast.ipynb      # Full analysis, models, reports
├── dataset/                  # Raw JHU CSV files
├── Problem Statement/        # Project brief
└── README.md
```

## How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/Akash250902/JohnsHopkins-Covid19-Forecasting.git
   cd JohnsHopkins-Covid19-Forecasting
   ```
2. Install the libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn statsmodels jupyter
   ```
3. Point the notebook to the data folder (optional, the default is `dataset/`):
   ```bash
   set COVID_DATA_DIR=dataset        # Windows
   export COVID_DATA_DIR=dataset     # macOS / Linux
   ```
4. Launch Jupyter and run all cells:
   ```bash
   jupyter notebook covid_forecast.ipynb
   ```

## Tech Stack

Python, Pandas, NumPy, Matplotlib, Seaborn, scikit-learn, statsmodels, Jupyter Notebook

## Author

**Akash**
GitHub: [@Akash250902](https://github.com/Akash250902)
