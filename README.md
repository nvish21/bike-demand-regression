# bike-demand-regression
Multiple Linear Regression model to predict daily bike demand (BoomBikes dataset)

# 🚲 Bike Demand Prediction — Multiple Linear Regression

### 📊 Project Overview
This project aims to predict the **daily demand for shared bikes** in the U.S. market using **Multiple Linear Regression**.  
The dataset was provided by **BoomBikes**, a bike-sharing provider looking to understand key factors that influence demand and prepare post-pandemic business strategies.

---

### 🎯 Business Objective
BoomBikes wanted to identify:
- Which variables significantly affect bike demand.
- How these factors quantitatively explain the variations in daily rentals.

The insights will help the company make informed decisions to optimize operations and marketing in future months.

---

### 🧮 Dataset Information
- **Total Records:** 730 (daily data for 2 years)
- **Target Variable:** `cnt` — total number of bikes rented per day.
- **Key Independent Variables:**
  - Season, Year, Month, Weather Situation
  - Temperature (`temp`), Humidity (`hum`), Windspeed (`windspeed`)
  - Working Day, Holiday, and Weekday flags

---

### 🔍 Project Steps
1. **Data Understanding & Cleaning**
   - Checked for missing values and duplicates → none found.
   - Converted encoded numeric fields (`season`, `weathersit`, `mnth`, etc.) into categorical strings.
   - Dropped redundant columns (`instant`, `dteday`, `casual`, `registered`, `atemp`).

2. **Exploratory Data Analysis (EDA)**
   - Visualized demand patterns across seasons, months, and weather.
   - Observed that demand increases with temperature and decreases with humidity/windspeed.
   - 2019 showed higher rentals than 2018, confirming growth trend.

3. **Feature Engineering**
   - Created dummy variables for categorical fields.
   - Split data into **Train (80%)** and **Test (20%)** sets.

4. **Model Building**
   - Built multiple linear regression model using `statsmodels.OLS`.
   - Iteratively refined model by removing high-VIF and insignificant variables.

5. **Model Evaluation**
   - **Training R²:** 0.834  
   - **Test R²:** 0.853  
   - **Test RMSE:** ~710  
   - **Test MAE:** ~554  
   - Residuals approximately normal and homoscedastic.

---

### 🔑 Key Insights
- **Temperature:** Strong positive impact on demand.  
- **Weather:** Misty or rainy days reduce rentals.  
- **Humidity & Windspeed:** Both negatively affect demand.  
- **Seasonal Patterns:** Higher usage in Fall/Winter; lowest in Spring.  
- **Trend:** Rentals increased significantly in 2019.

---

### 🧠 Tools & Libraries Used
- Python 3.x  
- Libraries:
  - `pandas`, `numpy`
  - `matplotlib`, `seaborn`
  - `statsmodels`, `sklearn`

---

### 📈 Results Summary
| Metric | Training | Test |
|:--|:--|:--|
| R² | 0.834 | 0.853 |
| RMSE | 794.7 | 710.3 |
| MAE |  —  | 554.4 |

Model successfully explains over **85% of the variation** in unseen data.

---

### 🗂️ Repository Structure
