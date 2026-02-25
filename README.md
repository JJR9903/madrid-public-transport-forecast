# Madrid Public Transport Demand Forecasting (NeuralProphet + SARIMA)

Forecast daily public transport demand in **Madrid (CRTM)** using classic statistical time-series models and NeuralProphet, with an emphasis on exploratory analysis, seasonality/trend decomposition, model selection, and out-of-sample validation.

## What’s inside

- **Exploratory analysis**
  - Time-series visualization
  - Trend + seasonality decomposition (via NeuralProphet)
- **SARIMA / SARIMAX workflow**
  - Differencing & stationarity checks
  - ACF/PACF inspection
  - Hyperparameter search and selection
  - Validation forecast and final forecast
- **NeuralProphet workflow**
  - Model identification and seasonality setup
  - Parameter grid search (incl. holiday effects)
  - Validation forecast and final forecast
  - Metrics (RMSE / MAE / MAPE)

## Data

The notebook expects an Excel file:

- `CRTM_Evolucion_demanda_diaria.xlsx` (sheet: `diaria`)

The data is loaded and reshaped into the standard Prophet/NeuralProphet format:

- `ds`: date
- `y`: total daily demand

## Results (from the notebook)

The best NeuralProphet configuration reports (test set):

- **RMSE:** ~432,079  
- **MAE:** ~256,483  
- **MAPE:** ~6.52%

(See the notebook outputs for full details and plots.)

## Getting started

### 1) Create an environment

```bash
python -m venv .venv
source .venv/bin/activate  # (Windows: .venv\Scripts\activate)
pip install -U pip
```

### 2) Install dependencies

```bash
pip install pandas numpy scikit-learn statsmodels joblib openpyxl matplotlib
pip install neuralprophet
pip install plotly plotly-resampler ipywidgets
```
## Repository structure (suggested)

```
.
├── NeuralProphet Madrid Public Transport.ipynb
├── CRTM_Evolucion_demanda_diaria.xlsx
├── README.md
└── .gitignore
```

## Notes / next steps

- Add holiday calendars for Madrid/Spain (official calendar) and compare impact.
- Try exogenous regressors (weather, strikes, fuel prices, major events).
- Add proper backtesting (rolling-origin evaluation).
- Export forecasts as CSV and add a lightweight dashboard.

## License

MIT License
