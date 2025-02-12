# 🏏 CricScoreX
![Screenshot 2025-02-12 094505](https://github.com/user-attachments/assets/da38ae77-1cfa-420d-b126-5fb4ebd322e4)

**CricScoreX** is a **Machine Learning Web App** designed to predict the final score of a **T20 cricket match** based on various match conditions. The model is trained using historical T20 match data and considers key features like the batting team, bowling team, venue, current score, overs bowled, wickets lost, and recent performance.

---
# Working Link

https://cricscorex.onrender.com/

---

## 🚀 Features

- **Predicts the final score** based on live match conditions.
- Uses **XGBoost Regressor** for accurate predictions.
- **Preprocessed dataset** with engineered features like run rate, wickets left, and recent form.
- **Web-based interface** for easy usage.

---

## 📊 Input Parameters

The model considers the following inputs:

- **Batting Team** 🏏  
- **Bowling Team** 🎯  
- **City** 🌍  
- **Current Score** 🏆  
- **Overs Completed** ⏳  
- **Wickets Fallen** ❌  
- **Runs in Last 5 Overs** 🔥  

---

## 🛠️ Tech Stack

- **Python 🐍**
- **Pandas, NumPy** (Data Processing)
- **Scikit-learn, XGBoost** (Machine Learning)
- **Flask** (Web Deployment)
- **Pickle** (Model Serialization)

---

## 📂 Dataset

The model is trained on **T20 International Cricket Data** (`t20i_info.csv`). Some key preprocessing steps include:

- Filling missing values for **city** based on venue.
- Filtering for cities with at least **600 matches** for consistency.
- **Feature Engineering**:
  - **Current Score**: Cumulative sum of runs per match.
  - **Balls Left**: Remaining balls in the innings.
  - **Wickets Left**: Total wickets fallen.
  - **Current Run Rate (CRR)**: `(Current Score * 6) / Balls Bowled`
  - **Runs in Last 5 Overs**: Rolling sum of runs in the last 30 balls.

---

## 🔮 Model Training

- The dataset is **split into training (80%) and testing (20%)**.
- A **Pipeline** is created using:
  - **OneHotEncoder** for categorical features.
  - **StandardScaler** for numerical features.
  - **XGBoost Regressor** for predictions.
- **Hyperparameters** used:
  - `n_estimators=1000`
  - `learning_rate=0.2`
  - `max_depth=12`
- **Performance Metrics**:
  - **R² Score**: (Measures model accuracy) - 0.9873261451721191
  - **Mean Absolute Error (MAE)**: (Evaluates prediction error) - 1.6409462690353394

---

## 🖥️ Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/karansaxena1/CricScoreX.git
   cd CricScoreX
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the web app:
   ```bash
   python app.py
   ```

4. Open your browser and navigate to:
   ```
   http://localhost:5000
   ```
   or  
   ```
   http://localhost:8501
   ```

---

## 📦 Deployment

The model is saved using **pickle** and can be deployed using **Flask** or **Streamlit**.

```python
import pickle
model = pickle.load(open('pipe.pkl', 'rb'))
prediction = model.predict(input_data)
```

---

## 📌 Future Improvements

- **Enhance the model** with more features (e.g., pitch conditions, weather data).
- **Optimize hyperparameters** for better accuracy.
- **Deploy as an API** for integration with cricket apps.

---

## 🎯 Conclusion

CricScoreX is a powerful tool for cricket enthusiasts, analysts, and developers looking to predict match scores using **Machine Learning**. 🚀

---

### 🔗 Connect

Feel free to contribute or reach out!  
📩 **Email**: karan.saxena1362@gmail.com  
🔗 **GitHub**: [CricScoreX Repo](https://github.com/karansaxena1/CricScoreX)
