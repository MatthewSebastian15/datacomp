# 🚍 Time Travel Estimation: Predicting Public Transport Travel Duration

## 📌 Description
This project aims to predict bus travel duration based on passenger transaction data. By leveraging tap-in/tap-out times, stop locations, travel distances, and temporal features, we built machine learning models that help transport operators provide accurate travel time estimations.

## 🔄 Process
### Data Loading
- Dataset sourced from public-transport.csv.
- Includes transaction details such as corridor, stops, tapInTime, tapOutTime, payAmount, etc.

### Data Cleaning & Preprocessing
- Handling missing values.
- Normalizing columns (CorridorID, CorridorName, Stops).
- Converting tapInTime into temporal features (day_of_week, tapInHour).
- Adding travel distance (distance_km) using OpenRouteService API.

### Feature Engineering
- Travel duration (difference between tap-in and tap-out).
- Additional features: passenger age, average speed, time category (Morning Rush, Midday, Evening Rush, Night).
- Outlier handling for extreme duration and distance values.

### Exploratory Data Analysis (EDA)
- Passenger distribution per hour.
- Top corridors and busiest stops.
- Fare distribution analysis.
- Correlation heatmap of numerical features.
- Travel duration comparison: weekday vs weekend.
- Daily passenger averages.


## ⚙️ Algorithms
### Random Forest Regressor
- Hyperparameter tuning with Optuna.
- Cross-validation for performance estimation.
- Feature importance to identify most influential variables.

### XGBoost Regressor
- Optimized using Optuna (learning rate, max depth, subsample, colsample_bytree).
- Compared against Random Forest.

## 📊 Results
Evaluation metrics: RMSE, MAE, and R²

<img width="386" height="113" alt="image" src="https://github.com/user-attachments/assets/95c2276b-af13-4338-b042-ed79385132c1" />

- Random Forest achieved the best performance with very low error and excellent generalization.
- XGBoost provided comparable results with faster training.

### Random Forest Regressor Scatter plots (Predicted vs Actual)
<img width="695" height="547" alt="image" src="https://github.com/user-attachments/assets/1441c070-e49e-472b-9a0c-f159695ae4de" />

### XGBoost Regressor Scatter plots (Predicted vs Actual)
<img width="695" height="547" alt="image" src="https://github.com/user-attachments/assets/c876cdea-3efa-41eb-93c9-8adbfdac3193" />


## Model Output 
### Senen → Kota (Corridor 7F)
![WhatsApp Image 2025-09-27 at 19 44 48_ffe00602](https://github.com/user-attachments/assets/5798b0f7-0e41-4f6d-8aec-8226e1ea30c1)
![WhatsApp Image 2025-09-27 at 19 44 48_4fdbd019](https://github.com/user-attachments/assets/07d1e3f1-1d08-4feb-bf47-15b77fda5d01)
![WhatsApp Image 2025-09-27 at 19 44 48_fbb62c37](https://github.com/user-attachments/assets/5c7f7c52-0e80-48e4-85b5-2e00d9d8272b)


### BKN → Ragunan (Corridor 7C)
![WhatsApp Image 2025-09-27 at 19 46 16_9efd2ac4](https://github.com/user-attachments/assets/dca76729-00f0-4cc7-9732-aa4149c4f44f)
![WhatsApp Image 2025-09-27 at 19 46 16_a5baf77f](https://github.com/user-attachments/assets/0a6b1d46-7b38-452b-a4b0-f503bb9a9c64)
![WhatsApp Image 2025-09-27 at 19 46 16_f84c4072](https://github.com/user-attachments/assets/30b1002a-e882-450b-9603-0b8f516aca0c)


## 🚀 Conclusion
- Best model: Random Forest with tuned hyperparameters → highly accurate predictions.
- Applications:
  - Optimizing bus schedules.
  - Providing reliable ETA for passengers.
  - Corridor and stop performance analysis.
