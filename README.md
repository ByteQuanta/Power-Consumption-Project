# Power Consumption Time Series Analysis
📘 Project Overview

This project focuses on time series analysis and forecasting of power consumption data from multiple zones within a smart grid environment.
Originally, the dataset contained combined data for all zones, but I manually separated each zone (Zone 1, Zone 2, etc.) into individual datasets to allow for zone-specific modeling and comparison.

Each zone is analyzed independently to better capture its unique consumption behavior, seasonal trends, and anomaly patterns.

## IMPORTANT NOTE: 
The source of the dataset used in this project is [Kaggle](https://www.kaggle.com/datasets/fedesoriano/electric-power-consumption)

🧩 Key Steps in the Pipeline

# 1. Data Preprocessing

1.1)Loaded and cleaned raw power consumption data.

1.2)Converted timestamps and resampled from 10-minute intervals to hourly averages.

1.3)Extracted temporal and seasonal features (hour, day of week, month, season, weekend flag).

# 2. Trend and Seasonality Analysis

2.1)Used statsmodels seasonal decomposition to visualize trend, seasonality, and residual components.

2.2)Calculated trend and seasonal strength to assess pattern dominance.

# 3. Stationarity Testing

3.1)Applied the Augmented Dickey-Fuller (ADF) test to check stationarity.

3.2)Visualized rolling mean and standard deviation.

# 4. Autocorrelation Analysis

4.1)Plotted ACF and PACF graphs.

4.2) Used the Ljung-Box test to assess autocorrelation significance.

# 5. Clustering-Based Anomaly Detection

5.1) Employed KMeans clustering (with lag features and differencing) to detect unusual consumption points.

5.2) Flagged the top 5% of distant points from cluster centers as anomalies.

# 6. Anomaly Cleaning

6.1) Implemented a neighbor mean replacement method to smooth anomaly points using surrounding data.

# 7. SARIMA Modeling with Optuna Optimization

7.1) Applied SARIMAX for forecasting cleaned hourly consumption.

7.2) Optimized train/test split ratio with Optuna for the best performance balance.

7.3) Evaluated model performance using MAE, MSE, and R² metrics.

# ⚙️ Technologies and Libraries

1) Python (Pandas, NumPy, Matplotlib, Seaborn)

2) Statsmodels – for ADF test, SARIMA, decomposition

3) Scikit-learn – for scaling, KMeans clustering

4) Optuna – for automatic hyperparameter optimization

5) Matplotlib / Plotly – for visualization

# 📊 Zones Analyzed

Zone 1: PowerConsumption_Zone1

Zone 2: PowerConsumption_Zone2

Zone 3: PowerConsumption_Zone3

🧩 Originally combined in a single dataset; separated into zone-specific CSV files (zone1.csv, zone2.csv, zone3.csv) for individual modeling and performance comparison.

# 🚀 Key Results

 Successfully identified and corrected anomalies in each zone.

 Observed strong daily and weekly seasonal patterns in both zones.

 Achieved robust SARIMA forecasts with optimized split ratios.

 Prepared clean, stationary series ready for advanced modeling (e.g., Prophet or LSTM).

# 📈 Future Work

 Implement Prophet and LSTM models for deep learning comparison.

 Develop a dashboard to visualize real-time consumption and anomaly alerts.
