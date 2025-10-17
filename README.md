# 🏠 House Pricing Prediction Project  

## 📘 Overview  
This project aims to **analyze and predict house prices in Egypt** using real estate data.  
It covers the full data science workflow — from **data cleaning** and **exploratory data analysis (EDA)** to **feature engineering** and **machine learning modeling**.  

The goal is to understand the factors that influence house prices and build a predictive model that can estimate property values with high accuracy.  

---

## 🧰 Libraries Used  
- pandas, numpy, missingno  
- matplotlib, seaborn  
- fuzzywuzzy, sklearn (LabelEncoder, train_test_split)  
- LinearRegression, Ridge, RandomForestRegressor, GradientBoostingRegressor  
- r2_score, mean_squared_error, mean_absolute_error  

---

## 🧹 Data Cleaning Steps  
1. Removed duplicates and unnecessary spaces.  
2. Standardized text (lowercasing, stripping whitespace).  
3. Cleaned inconsistent entries in categorical columns.  
4. Removed or kept `NaN` values strategically based on relevance.  
5. Normalized key categorical variables such as `Furnished`, `Payment_Option`, and `Delivery_Term`.  

📊 **Final Shape:** 25,433 rows × 12 columns  
📉 **Memory Usage:** ~1.27 MB after cleaning  

---

## 🔍 Exploratory Data Analysis (EDA)

### 🧩 Key Insights  
- **Price & Area** are right-skewed — most properties are in a moderate range, with few luxury outliers.  
- **Bedrooms/Bathrooms:** Most houses have 2–4 bedrooms and 1–3 bathrooms.  
- **Furnished:** ~9% of listings are furnished — most are unfurnished for long-term ownership.  
- **Cities:** Listings are concentrated in *New Cairo* and *North Coast*.  
- **Correlation:** Strongest correlations with price are **Bathrooms (0.56)** and **Area (0.52)**.  

---

## 🧩 Feature Engineering  
Added new and transformed features for better prediction performance:  
- `price_per_m2` → Price divided by Area.  
- `total_rooms` → Sum of Bedrooms and Bathrooms.  
- Log-transformed `Price` and `Area` for better normalization.  
- Label encoded categorical variables (`City`, `Type`, `Furnished`, `Delivery_Term`).  
- Dropped irrelevant columns (`Compound`, `Developer`).  

---

## 🧠 Machine Learning Models  

### Models Trained  
- Linear Regression  
- Ridge Regression  
- Random Forest Regressor  
- Gradient Boosting Regressor  

### Performance Summary  
| Model | R² | RMSE | MAE |
|-------|------|-----------|-----------|
| Gradient Boosting | 0.9998 | 86,932 | 34,919 |
| Random Forest | 0.9990 | 182,126 | 4,338 |
| Ridge Regression | 0.837 | 2,406,109 | 1,498,740 |
| Linear Regression | 0.837 | 2,406,134 | 1,498,759 |

✅ **Best Model:** Gradient Boosting Regressor  
→ Achieved almost perfect fit with lowest RMSE and MAE values.

### 💾 Model File
The trained Gradient Boosting model is saved as: **model/gradient_boosting_model.pkl**


---

## 🧾 Conclusion  
- **Bathrooms** and **Area** are the most influential features affecting price.  
- The **Gradient Boosting Regressor** provided the most accurate price predictions.  
- Future improvements could include:
  - Adding location-based features (latitude, longitude).  
  - Incorporating economic indicators or developer reputation.  
  - Using ensemble stacking or neural networks for further optimization.

---

## 👨‍💻 Author  
**Osama Othman**  
📧 [osmanosamaahmed@gmail.com]  
💼 [LinkedIn Profile](www.linkedin.com/in/osama-othman-a78141368)  
🌐 [GitHub Profile](https://github.com/osamaAhmedOthman)  
