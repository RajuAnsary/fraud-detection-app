# 💳 Fraud Detection Prediction App

An end-to-end **Machine Learning powered Fraud Detection Web Application** built using **Python, Scikit-learn, and Streamlit**, capable of identifying potentially fraudulent financial transactions in real time.

🔗 **Live Demo**  
https://fraud-detection-app-1-412j.onrender.com/

---

## 📌 Project Overview

Digital payment fraud is a major challenge in modern financial systems.  
This project predicts whether a transaction is fraudulent by analyzing transaction behavior using machine learning.

The project covers:

- Exploratory Data Analysis (EDA)
- Fraud pattern analysis
- Feature engineering
- Model comparison
- Random Forest based fraud prediction
- Interactive Streamlit deployment

---

## ✨ Features

- Real-time Fraud Prediction
- Interactive Streamlit Web App
- Machine Learning Pipeline Integration
- Transaction Risk Classification
- Model Comparison (Logistic Regression vs Random Forest)
- Deployed Live on Render

---

# 📊 Exploratory Data Analysis

## Transaction Type Distribution

Key findings:

- PAYMENT has highest transaction volume
- CASH_OUT is the second most frequent
- Fraud mainly occurs in:
  - TRANSFER
  - CASH_OUT

---

## Fraud Rate by Transaction Type

Fraud concentration is highest in:

- TRANSFER  
- CASH_OUT

PAYMENT and DEBIT show almost no fraud activity.

---

## Transaction Amount Analysis

Using log-scaled distribution analysis:

- Multi-modal transaction amount behavior observed
- Certain amount ranges show suspicious concentration
- Useful signal for fraud detection

---

# 🤖 Model Development

## Baseline Model: Logistic Regression

### Performance

Accuracy:

```text
82.22%
```

Classification Report:

| Metric | Fraud Class |
|--------|-------------|
| Precision | 0.01 |
| Recall | 0.97 |
| F1 Score | 0.01 |

Confusion Matrix:

```text
[[22386 4846]
 [1 33]]
```

### Observation

- High fraud recall  
- Extremely poor precision  
- Too many false positives  
- Not suitable for deployment

---

# ✅ Final Model: Random Forest Classifier

Pipeline Components:

- StandardScaler
- OneHotEncoder
- ColumnTransformer
- RandomForestClassifier (class_weight="balanced")

---

## Final Model Performance

Accuracy:

```text
99.91%
```

Classification Report:

| Metric | Fraud Class |
|--------|-------------|
| Precision | 0.92 |
| Recall | 0.35 |
| F1 Score | 0.51 |

Confusion Matrix:

```text
[[27231 1]
 [22 12]]
```

---

## Why Random Forest Was Selected

Compared with Logistic Regression:

✔ Higher accuracy  
✔ Lower false positives  
✔ Better fraud precision  
✔ More reliable deployment model

---

# 🧪 Input Features Used

The model predicts fraud using:

- Transaction Type
- Amount
- Old Balance (Sender)
- New Balance (Sender)
- Old Balance (Receiver)
- New Balance (Receiver)

---

# 🛠 Tech Stack

- Python
- Streamlit
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib
- Render

---

# 📂 Project Structure

```bash
fraud-detection-app/
│
├── fraud_detection.py
├── fraud_detection_pipeline.pkl
├── requirements.txt
└── README.md
```

---

# ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/RajuAnsary/fraud-detection-app.git
cd fraud-detection-app
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run locally:

```bash
streamlit run fraud_detection.py
```

---

# 🚀 Deployment

Deployed using **Render**

Live App:

https://fraud-detection-app-1-412j.onrender.com/

---

# 🖥 Usage

1. Select transaction type  
2. Enter balances and amount  
3. Click Predict  
4. View fraud prediction result

---

## Example Output

Fraud detected:

```text
Prediction: Fraudulent Transaction
```

Legitimate:

```text
Prediction: Non-Fraudulent Transaction
```



# 🔮 Future Improvements

- XGBoost / LightGBM comparison
- SHAP explainability
- Fraud probability scoring
- Real-time transaction API
- Fraud analytics dashboard

---

# 👨‍💻 Author

**Raju Ansary**  
Aspiring Full Stack Developer | Machine Learning Enthusiast

GitHub: https://github.com/RajuAnsary

---

## 📄 License

This project is for educational and portfolio purposes.
