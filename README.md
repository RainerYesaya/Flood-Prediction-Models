---

# 🌧️ Flood Prediction Model – Jakarta (Machine Learning Project)

This project focuses on predicting flood risk in Jakarta using historical weather data. The model is built using a **Random Forest Classifier** and deployed through a simple **Flask** web application.
The goal is to provide an accessible early-warning tool based on real climate patterns.

---

## 📌 Background

Jakarta is one of the most flood-prone cities in Indonesia. Contributing factors include extreme rainfall, humidity, wind speed, rapid urbanization, land subsidence, and inadequate drainage systems.

This project aims to:

* Analyze Jakarta's historical climate data
* Build a more reliable flood prediction model
* Deliver predictions through a lightweight, user-friendly web interface

Dataset used: *Climate and Flood Jakarta 2016–2020* (Kaggle).

---

## 🧹 Data Preparation

### **1. Handling Missing Values**

* Numerical features → filled with mean
* Categorical features → filled with mode

### **2. Feature Engineering**

Added time-based features:

* Year
* Month
* Day
* Day of week

### **3. Encoding**

Categorical columns such as wind direction, station name, and region were converted using Label Encoding.

### **4. Splitting & Balancing**

* 80% training, 20% testing
* SMOTE was applied on the training set to address class imbalance

---

## 🤖 Machine Learning Model

A **Random Forest Classifier** was selected due to its robustness, strong performance on tabular data, and ability to capture nonlinear relationships.

Two scenarios were evaluated:

### **1. Without SMOTE**

* Accuracy: **93%**
* Flood recall: **0.08** → model is biased toward the majority class

### **2. With SMOTE**

* Accuracy: **90%**
* Flood recall: **0.18** → better at detecting actual flood events

Even though accuracy slightly decreases, recall improvement is more valuable for disaster prediction.

---

# 📦 Requirements

 All required dependencies are already included in the `requirements.txt`file in this repository.
To install them:
```bash
pip install -r requirements.txt
```
This will automatically install all the libraries used for preprocessing, training, and deploying the model.
---

## 🌐 Flask Web Application

The model is served through a Flask interface where users can input:

* Humidity (%)
* Temperature (°C)
* Average Wind Speed (knots)
* Rainfall (mm)

The output includes:

* Flood risk percentage for each region in Jakarta
* Risk label: **UNLIKELY** (green) / **LIKELY** (red)
* Color indicators for clarity
* Prediction history

---

---

## 🚀 How to Run

1. Clone the repository:

```bash
git clone https://github.com/RainerYesaya/Flood-Prediction-Models.git
cd <your-project-folder>
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Run the Flask app:

```bash
python app.py
```

4. Open in the browser:

```
http://127.0.0.1:5000/
```

---

## 📊 Key Findings

* The baseline model has high accuracy but performs poorly in identifying flood events.
* SMOTE significantly improves the model’s recall for the flood class.
* For disaster-related predictions, recall is more critical than accuracy.

---

## 👨‍💻 Team Members

* **Rainer Yesaya Villareal** – ML model, preprocessing, implementation, evaluation
* **Vincenzo Christi Azarya** – Flask UI, methodology, evaluation
* **Nicole Alexandra Yauwrentius** – ML model, Flask UI, background & problem statement

---



