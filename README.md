🚲 Rental Bike Sharing Demand Prediction – README
📌 Objective
The aim of this project is to predict the number of rental bikes required on a given day/hour based on environmental and seasonal settings such as temperature, humidity, weather conditions, day of the week, and more. Accurate predictions help bike-sharing companies manage resources efficiently and improve user satisfaction.

📁 Dataset Information
Source: UCI Machine Learning Repository

Files:

day.csv – daily data

hour.csv – hourly data

Records: ~17,000 rows (hourly data)

Target Variable: count – total number of bikes rented

🔑 Key Features
Feature	Description
season	Season (1:spring, 2:summer, 3:fall, 4:winter)
yr	Year (0:2011, 1:2012)
mnth	Month (1 to 12)
hr	Hour (0 to 23) – hour.csv only
holiday	Whether the day is a holiday
weekday	Day of the week
workingday	If day is neither weekend nor holiday
weathersit	Weather situation (1 to 4)
temp	Normalized temperature
atemp	Normalized feeling temperature
hum	Normalized humidity
windspeed	Normalized wind speed
casual	Count of casual users (not used for prediction)
registered	Count of registered users (not used for prediction)
count	Total count (casual + registered) – target variable

🧹 Data Preprocessing
Handled missing values (if any)

Converted categorical columns to categorical data types

Applied one-hot encoding for non-ordinal categories

Detected and removed outliers using IQR/z-score methods

Performed feature scaling (e.g., Min-Max Scaling for some models)

🔧 Feature Engineering
Extracted new features:

day_part (morning, afternoon, evening, night)

is_weekend

season_name, hour_bin

Dropped irrelevant features like instant, dteday (if datetime parsing done)

🧠 Models Used
Linear Regression

Ridge & Lasso Regression

Random Forest Regressor

XGBoost Regressor

Gradient Boosting

Stacking Regressor (Ensemble)

🧪 Evaluation Metrics
Evaluated model performance using:

Metric	Description
R² Score	Proportion of variance explained by model
RMSE	Root Mean Squared Error
MAE	Mean Absolute Error
Cross-Validation	5-Fold CV for robust results


📈 Results
Model	R² Score	RMSE	MAE
Linear Regression	0.60–0.65	130–150	100–120
Random Forest	0.90+	< 50	~30
XGBoost	0.92+	< 40	< 25
Stacking Regressor	0.94+	< 35	< 20

📊 Visualizations
Correlation Heatmap

Feature Importance Bar Chart

Boxplots for Outlier Detection

Actual vs Predicted Count Plot

Time Series Trend Line

✅ Key Takeaways
Temperature and hour of day are strong predictors of demand

Humidity and weather condition also affect rentals

Weekends and holidays have different demand patterns

🚀 Future Improvements
Deploy as a Flask web app for real-time prediction

Use Deep Learning (LSTM) for time series forecasting

Add external data like local events, real-time weather

