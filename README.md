# 🗽 NYC Taxi Trip Data Analysis & High Tip Prediction

This project focuses on cleaning, analyzing, and modeling New York City yellow taxi trip data to uncover patterns and predict the likelihood of high tipping behavior. The project leverages **Python** for data cleaning and engineering, and **Apache Spark (PySpark)** for large-scale analytics and machine learning with **SparkML**.

## 📊 Project Goals

- Clean and preprocess raw trip and location data.
- Generate actionable insights using analytical queries.
- Build predictive models to classify trips likely to result in high tips.

---

## 📁 Dataset Description

The project uses two main datasets:
1. **`taxitripdata.csv`** – Contains raw trip-level data (e.g., fare, tip, pickup/dropoff times and locations).
2. **`taxizonegeo.csv`** – Maps pickup/dropoff zone IDs to boroughs and zone names.

---

## 🔧 Technologies Used

- **Python 3.10+**
- **Pandas**, **NumPy**
- **PySpark (Spark 3.x)**
- **Spark SQL**, **SparkML**
- **Matplotlib**, **Seaborn** (for EDA visualizations)

---

## ⚙️ Data Cleaning & Feature Engineering (Python)

- Handled missing values (e.g., nulls, empty strings, invalid entries).
- Dropped duplicate rows and irrelevant columns.
- Created engineered features such as:
  - `trip_duration_minutes` (from pickup and dropoff timestamps)
  - `total_fare` (sum of fare, extras, tax, tip, tolls)
- Merged zone-level data from `taxizonegeo.csv` for geospatial context.

---

## 📈 Analytical Insights (PySpark)

Executed Spark SQL and DataFrame queries to answer business questions:
- Most common **payment types** per time of day.
- **Top-earning boroughs** and **high-volume pickup locations**.
- **Average tips by passenger count**.
- **Top 5 longest trips** and unusual fare patterns.
- Most frequent **inter-borough routes** and their revenue breakdowns.

---

## 🤖 ML Task: Predicting High Tip Likelihood

- Defined binary target:  
  `high_tip = 1` if `tip_amount > 15% of fare`, else `0`.
- ML features:
  - Passenger count
  - Trip duration
  - Trip distance
  - Fare amount
  - Pickup hour (time of day)
  - Fare per mile
- Used **VectorAssembler** to combine features.
- Trained and evaluated:
  - Logistic Regression
  - Decision Tree
  - Random Forest
- Compared accuracy and interpreted feature importance.

---

## 📊 Results

- Identified optimal model and most influential features.
- Demonstrated how real-world trip characteristics can predict tipping behavior.
