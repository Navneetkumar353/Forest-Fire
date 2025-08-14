# 🌲 Forest Fire Prediction – Ridge/Lasso Regression & Flask Deployment

## 📖 Project Brief

This project is a **machine learning-powered Fire Weather Index (FWI) prediction system** built using **Ridge** and **Lasso** regression techniques.
It takes key meteorological inputs — such as temperature, relative humidity, wind speed, rainfall, and fire-related indices (FFMC, DMC, ISI, Classes, Region) — and predicts the **FWI value**, which indicates the likelihood and potential intensity of forest fires.

The workflow covers:

* **Data preprocessing & feature scaling**
* **Model training & evaluation** using Ridge and Lasso regression
* **Model serialization** with Pickle for deployment
* **Flask web app** that allows users to input parameters via a web form and instantly get predictions

This project demonstrates the **complete ML lifecycle** from **exploration → training → deployment** in a real-world use case.

---

## 📌 Project Overview

This repository contains:

* **Exploratory and Model Training Notebooks** for Ridge and Lasso regression.
* **Pickled Model Artifacts** (`ridge.pkl`, `scaler.pkl`) for deployment.
* A **Flask Web Application** to serve predictions through a simple HTML form.

---

## 📂 Repository Structure

```
├── Ridge_Laso regression.ipynb     # Notebook exploring Ridge & Lasso regression
├── Model Training.ipynb            # Full training pipeline, preprocessing, and saving models
├── models/
│   ├── ridge.pkl                    # Trained Ridge Regression model
│   ├── scaler.pkl                   # StandardScaler used during training
├── application.py                   # Flask app serving predictions
├── templates/
│   ├── index.html                   # Home page
│   ├── home.html                    # Prediction form & output display
├── requirements.txt                 # Dependencies list
└── README.md                        # Project documentation
```

---

## 🛠 Installation

```bash
git clone https://github.com/your-username/fwi-prediction.git
cd fwi-prediction
pip install -r requirements.txt
```

---

## 📖 Notebooks

### **1. Ridge\_Laso regression.ipynb**

* Demonstrates Ridge & Lasso regression concepts.
* Compares coefficients and performance metrics.
* Explores regularization parameter effects.

### **2. Model Training.ipynb**

* Loads dataset and preprocesses using `StandardScaler`.
* Trains Ridge Regression model.
* Saves:

  ```python
  import pickle
  pickle.dump(scaler, open('models/scaler.pkl', 'wb'))
  pickle.dump(ridge, open('models/ridge.pkl', 'wb'))
  ```

---

## 🚀 Running the Flask App

```bash
python application.py
```

Open in browser: `http://127.0.0.1:5000`

---

## 💾 Model Artifacts

* **`scaler.pkl`** → StandardScaler for input normalization.
* **`ridge.pkl`** → Trained Ridge Regression model.

```python
import pickle
scaler = pickle.load(open('models/scaler.pkl', 'rb'))
ridge = pickle.load(open('models/ridge.pkl', 'rb'))
```

---

## 🌟 Future Enhancements

* Add **Lasso** and **ElasticNet** prediction options in the app.
* Implement **model comparison dashboard** in Flask UI.
* Deploy on **AWS Elastic Beanstalk**.

