# Power Consumption Time Series Analysis
📘 Project Overview

This project focuses on time series analysis and forecasting of power consumption data from multiple zones within a smart grid environment.
Originally, the dataset contained combined data for all zones, but I manually separated each zone (Zone 1, Zone 2, etc.) into individual datasets to allow for zone-specific modeling and comparison.

Each zone is analyzed independently to better capture its unique consumption behavior, seasonal trends, and anomaly patterns.

## IMPORTANT NOTE: 
The source of the dataset used in this project is [Kaggle](https://www.kaggle.com/datasets/fedesoriano/electric-power-consumption)

🧩 Key Steps in the Pipeline

1. Data Preprocessing

# Loaded and cleaned raw power consumption data.

# Converted timestamps and resampled from 10-minute intervals to hourly averages.

# Extracted temporal and seasonal features (hour, day of week, month, season, weekend flag).

2. Trend and Seasonality Analysis

# Used statsmodels seasonal decomposition to visualize trend, seasonality, and residual components.

# Calculated trend and seasonal strength to assess pattern dominance.

3. Stationarity Testing

# Applied the Augmented Dickey-Fuller (ADF) test to check stationarity.

# Visualized rolling mean and standard deviation.

4. Autocorrelation Analysis

# Plotted ACF and PACF graphs.

# Used the Ljung-Box test to assess autocorrelation significance.

5. Clustering-Based Anomaly Detection

# Employed KMeans clustering (with lag features and differencing) to detect unusual consumption points.

# Flagged the top 5% of distant points from cluster centers as anomalies.

6. Anomaly Cleaning

# Implemented a neighbor mean replacement method to smooth anomaly points using surrounding data.

7. SARIMA Modeling with Optuna Optimization

# Applied SARIMAX for forecasting cleaned hourly consumption.

# Optimized train/test split ratio with Optuna for the best performance balance.

# Evaluated model performance using MAE, MSE, and R² metrics.

⚙️ Technologies and Libraries

# Python (Pandas, NumPy, Matplotlib, Seaborn)

# Statsmodels – for ADF test, SARIMA, decomposition

# Scikit-learn – for scaling, KMeans clustering

# Optuna – for automatic hyperparameter optimization

# Matplotlib / Plotly – for visualization

📊 Zones Analyzed

Zone 1: PowerConsumption_Zone1

Zone 2: PowerConsumption_Zone2

Zone 3: PowerConsumption_Zone3

🧩 Originally combined in a single dataset; separated into zone-specific CSV files (zone1.csv, zone2.csv, zone3.csv) for individual modeling and performance comparison.

🚀 Key Results

# Successfully identified and corrected anomalies in each zone.

# Observed strong daily and weekly seasonal patterns in both zones.

# Achieved robust SARIMA forecasts with optimized split ratios.

# Prepared clean, stationary series ready for advanced modeling (e.g., Prophet or LSTM).

📈 Future Work

# Implement Prophet and LSTM models for deep learning comparison.

# Develop a dashboard to visualize real-time consumption and anomaly alerts.
