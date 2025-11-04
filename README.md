The goal of this analysis is to forecast daily passenger counts for different public transport service types — Local Route, Light Rail, Peak Service, Rapid Route, and School. The dataset consists of daily journey counts over multiple years, allowing trend, seasonality, and correlation analysis.
 Based on statistical testing and model evaluation, the ARIMA (AutoRegressive Integrated Moving Average) model was chosen for forecasting due to its strong performance on stationary time series data.
 The ARIMA model is a classic statistical time series forecasting technique that combines three components:1.AR (AutoRegressive) 2.I (Integrated) 3.MA (Moving Average).The general ARIMA model is denoted as ARIMA(p, d, q).
3. Steps Performed
  Data Cleaning & Aggregation:
  Missing values in individual service columns (e.g., “Other”) were filled using mean imputation.
  A new column Total_Passengers was created by summing all service types.
  Stationarity Check (ADF Test):
  The Augmented Dickey–Fuller (ADF) test returned a p-value < 0.05, confirming that the series is stationary.
  Hence, differencing (d = 0) was not required.

Model Selection (p, d, q):
Multiple ARIMA configurations were tested, and ARIMA(0, 0, 2) achieved the lowest AIC (41935), indicating the best balance of fit and complexity.

Model Training & Forecasting:
The model was trained on historical passenger data to generate a 7-day forecast for each service type.
Predictions closely followed observed trends.

Performance Evaluation:

Mean Absolute Error (MAE): ~13,300

Root Mean Squared Error (RMSE): ~23,100
These errors are acceptable given the scale (daily passengers in tens of thousands).

Conclusion:
    Insights from Model

Passenger counts show strong weekly seasonality and mild long-term growth.

Forecasted trends indicate a steady increase in overall ridership.

Local Route remains dominant, with School services showing cyclical peaks.

The ARIMA model effectively captures these short-term fluctuations.
The ARIMA(0, 0, 2) model successfully forecasts near-term passenger counts with reasonable accuracy.
Its interpretability, simplicity, and strong statistical foundation make it suitable for short-term forecasting in public transport analytics.
For future improvements, SARIMA or Prophet models could be explored to capture complex seasonal patterns or holiday effects.

KEY INSIGHTS TO PROVIDE:
1.Observation: Passenger numbers are higher on weekdays and drop on weekends.
Action:

Run more buses/trains on weekdays (especially Monday–Friday mornings and evenings).


2.Observation: The “School” service spikes during school months and nearly drops to zero during vacations.
 Action:

Use school buses for other routes during holidays (to avoid idle assets).

Automatically adjust schedules before/after vacation periods.

3.Dynamic Peak-Hour Scheduling

 Observation: “Peak Service” and “Local Route” have a strong positive correlation.
 Action:

Increase frequency between 7–10 AM and 5–8 PM (office commute hours).

Reduce frequency during mid-day when ridership is low.

4.Event & Holiday-based Campaign Planning

 Observation: Sharp drops or spikes in total passengers correspond to holidays or public events.
 Action:

During major events (like Diwali, Pongal, or sports matches), deploy extra temporary routes.


