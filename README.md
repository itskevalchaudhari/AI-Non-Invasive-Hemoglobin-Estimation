# AI Non-Invasive Hemoglobin Estimation

AI-based estimation of hemoglobin levels using Photoplethysmography (PPG) signals and machine learning.

## 📌 Project Overview

This project investigates the feasibility of estimating hemoglobin (Hb) levels using non-invasive optical PPG signals along with demographic information.

The project uses Red and Infrared PPG signal measurements, age, and gender as input features. Machine learning regression models are used to estimate the corresponding hemoglobin level.

> **Note:** This project is a feasibility study and educational research project. It is not a medical diagnostic device and should not be used for clinical diagnosis or treatment decisions.

---

## 🎯 Objective

The main objectives of this project are:

- To study the relationship between PPG signals and hemoglobin levels.
- To preprocess and analyze PPG-based data.
- To engineer useful features from Red and Infrared PPG signals.
- To train machine learning regression models for hemoglobin estimation.
- To evaluate the models using MAE, RMSE, and R².
- To develop a simple interactive prediction interface using Gradio.

---

## 📊 Dataset

The project uses the **Hemoglobin Photoplethysmography Dataset**.

### Dataset Information

- Number of subjects: **68**
- Total measurements/rows: **816**
- Female subjects/measurements: **456**
- Male subjects/measurements: **360**
- Age range: **18–64 years**
- Target variable: **Hemoglobin (g/dL)**

### Main Features

| Feature | Description |
|---|---|
| Red (a.u) | Red-channel PPG signal |
| Infra Red (a.u) | Infrared-channel PPG signal |
| Age (year) | Age of the subject |
| Gender | Gender of the subject |
| Hemoglobin (g/dL) | Target hemoglobin value |

### Dataset Source

Hemoglobin Photoplethysmography Dataset, Mendeley Data, Version 2.

DOI: **10.17632/xdrwrh9zbk.2**

License: **CC BY 4.0**

---

## 🧠 Methodology

The overall workflow of the project is:

1. Load the PPG dataset.
2. Perform exploratory data analysis.
3. Check missing values and basic statistics.
4. Encode categorical gender information.
5. Perform feature engineering.
6. Split the data for model development and evaluation.
7. Train machine learning regression models.
8. Evaluate model performance.
9. Analyze feature importance and prediction errors.
10. Build an interactive Gradio prediction interface.

### Feature Engineering

Additional features were derived from the Red and Infrared PPG signals:

- Red/Infrared Ratio
- Red/Infrared Difference
- Red/Infrared Sum

The final model uses:

- Red PPG
- Infrared PPG
- Age
- Gender
- Red/Infrared Ratio
- Red/Infrared Difference
- Red/Infrared Sum

---

## 🤖 Machine Learning Model

A **Random Forest Regressor** was used for the main prediction model.

The model combines PPG-based features with demographic information to estimate hemoglobin levels.

### Evaluation Metrics

The model was evaluated using:

- **MAE (Mean Absolute Error)**
- **RMSE (Root Mean Squared Error)**
- **R² Score**

---

## 📈 Results

Subject-level evaluation of the models produced the following results:

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Demographic-Only Random Forest | 1.152 | 1.310 | 0.044 |
| PPG + Demographic Random Forest | 0.770 | 0.916 | 0.533 |
| Subject-Level Linear Regression | 0.896 | 1.119 | 0.302 |

The results indicate that combining PPG-derived features with demographic information provided useful predictive information for this dataset.

However, the dataset is relatively small at the subject level, so these results should be interpreted as a feasibility study rather than evidence of clinical performance.

---

## 🔍 Feature Importance

The Random Forest model was also analyzed to understand the contribution of different features.

Important features included:

- Age
- Gender
- Red/Infrared Difference
- Red/Infrared Ratio
- Red PPG
- Infrared PPG
- Red/Infrared Sum

Feature importance helps understand which input variables contributed most to the model's predictions.

---

## 🖥️ Interactive Prediction Interface

A **Gradio-based interface** was developed to allow users to enter:

- Red PPG value
- Infrared PPG value
- Age
- Gender

The application automatically calculates the engineered PPG features and provides an estimated hemoglobin value using the trained Random Forest model.

---

## ▶️ How to Run

### Option 1: Google Colab

1. Open the Jupyter Notebook:
   `AI_Non_Invasive_Hemoglobin_Estimation.ipynb`
2. Open it in Google Colab.
3. Run the cells from top to bottom.
4. When prompted, upload:
   `Final Dataset Hb PPG.csv`
5. Allow the required Python libraries to install.
6. Run the machine learning and evaluation cells.
7. Run the final Gradio cell.
8. Use the interactive interface to test the trained model.

### Required Libraries

The project uses Python libraries such as:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- gradio

---

## 📁 Repository Structure

```text
AI-Non-Invasive-Hemoglobin-Estimation/
│
├── AI_Non_Invasive_Hemoglobin_Estimation.ipynb
├── Final Dataset Hb PPG.csv
└── README.md
