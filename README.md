# 🥑 Avocado Ripeness Classification

This project builds an end-to-end machine learning pipeline to classify the ripeness level of avocados using sensor and color-based data. It covers Exploratory Data Analysis (EDA), preprocessing, model training, evaluation, and saving results.

---

## 📌 Problem Statement

Accurately determining the ripeness of avocados is crucial for reducing waste, improving logistics, and delivering quality produce to consumers. This project classifies avocado ripeness into five categories based on various non-image sensor readings and color measurements.

---

## 🧠 Objective

Create a supervised machine learning model that can predict the **ripeness stage** of an avocado using numerical features like firmness, hue, saturation, brightness, sound response, and size.

Target Classes:
1. Hard  
2. Pre-conditioned  
3. Breaking  
4. Firm-ripe  
5. Ripe

---

## 📂 Project Structure

avocado-ripeness-classification/
│
├── data/
│ ├── raw/ # Raw CSV file
│ └── processed/ # Preprocessed (scaled/split) data
│
├── notebooks/
│ ├── eda.ipynb # Exploratory Data Analysis
│ └── model_training.ipynb # Training and evaluating models
│
├── models/
│ └── best_model.pkl # Saved trained model
│
├── outputs/
│ └── metrics.json # Evaluation metrics (accuracy, F1, etc.)
│
├── utils/
│ └── preprocessing.py # Functions for scaling, encoding, etc.
│
├── README.md # Project documentation
└── requirements.txt # Python dependencies

yaml
Copy
Edit

---

## 📊 Dataset Description

The dataset contains sensor readings of avocados. Here are the features:

| Feature         | Description                              | Unit         | Pattern                           |
|----------------|------------------------------------------|--------------|-----------------------------------|
| `firmness`     | Resistance to penetration                | 10–100 N     | Hard: 80-100, Ripe: 10-20         |
| `hue`          | Color wavelength                         | 0–360°       | Green → Purple → Black            |
| `saturation`   | Color intensity                          | 0–100%       | Decreases with ripeness           |
| `brightness`   | Color lightness                          | 0–100%       | Darkens with ripeness             |
| `color_category`| Skin color category                     | Categorical  | Green, Purple, Black              |
| `sound_db`     | Tap sound intensity                      | 30–80 dB     | Lower = riper                     |
| `weight_g`     | Weight                                   | 150–300g     | Decreases with ripeness           |
| `size_cm3`     | Volume                                   | 100–300cm³   | Increases with ripeness           |
| `ripeness`     | **Target** variable (5 stages)           | Categorical  | Multiclass classification         |

---

## 🚀 Pipeline Steps

1. **EDA**: Univariate and multivariate analysis, outlier treatment, class imbalance check.
2. **Preprocessing**: Scaling, encoding, train-test split.
3. **Model Training**: RandomForest, XGBoost, etc.
4. **Evaluation**: Accuracy, precision, recall, F1-score.
5. **Model Saving**: Save best-performing model using `joblib`.
6. **Modular Design**: Utilities for reusability and clarity.

---

## 🔍 How to Run the Project

### 1. Clone the Repository

```bash
git clone https://github.com/kraj2003/avocado-ripeness-classification.git
cd avocado-ripeness-classification
