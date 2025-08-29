# 💻 Laptop Price Predictor  

Ever wondered how much your dream laptop should cost? 🤔  
This project is a **Machine Learning model** that predicts the price of a laptop based on its configuration — things like **RAM, CPU, GPU, brand, OS, touchscreen, weight, and more**.  

I trained this model using a dataset of laptops and deployed it with a simple interface so you can test it yourself! 🚀  

---
✅ **[Try it out here!](https://laptop-predictor-vimo.streamlit.app/)** 🚀  

## 📊 Dataset & EDA  
- Cleaned the dataset by dropping unnecessary columns like `Cpu`, `Cpu Name`, `Memory` (after feature engineering).  
- Extracted useful features such as:  
  - Whether the screen is **Touchscreen** or not  
  - Whether it has an **IPS panel**  
  - Screen **resolution & PPI**  
  - Encoded categorical variables like **Company, TypeName, OS, GPU Brand** using `OneHotEncoder`.  
- Handled missing values & ensured consistent formatting for numerical + categorical columns.  
- Target variable: **Laptop Price (log-transformed for stability)**.  

---

## ⚙️ Model Building  
- Used a **Pipeline** for preprocessing + model training.  
- Steps:  
  1. `ColumnTransformer` → One-hot encoding for categorical features.  
  2. `RandomForestRegressor` as the main model.  
- Hyperparameters tuned:  
  - `n_estimators=100`  
  - `max_depth=15`  
  - `max_features=0.75`  
  - `max_samples=0.5`  

---

## 📈 Performance  
- Evaluated on **test data**.  
- 📌 **R² Score:** ~0.86  
- 📌 **Mean Absolute Error (MAE):** ~0.19 (after taking exp back from log)  

Pretty solid for predicting real-world laptop prices .  

---

## 🛠️ Tech Stack  
- **Python** 
- **Scikit-learn** (ML model)  
- **Pandas, NumPy** (data wrangling)  
- **Matplotlib, Seaborn** (EDA & plots)  
- **Streamlit** (for deployment / frontend)  
