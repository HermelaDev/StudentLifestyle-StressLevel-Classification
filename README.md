<p align="center">
  <img src="cartoon-character.avif" alt="Cartoon Character" width="500"/>
</p>

# 📘 Student Lifestyle & Stress Level Classification  
A Machine Learning Project

This project analyzes how students’ study habits, sleep duration, social time, physical activity, and academic performance relate to **stress levels**.  
Using a dataset of 2,000 students, the project includes **EDA**, **data preprocessing**, **classification modeling**, **feature importance analysis**, and an interactive **Gradio prediction app**.

---

## 📊 Dataset Overview

- **Rows:** 2000  
- **Columns:** 8  

### **Features**
- Study_Hours_Per_Day  
- Extracurricular_Hours_Per_Day  
- Sleep_Hours_Per_Day  
- Social_Hours_Per_Day  
- Physical_Activity_Hours_Per_Day  
- GPA  
- Stress_Level *(target)*

### **Target Encoding**
- **Low → 0**  
- **Moderate → 1**  
- **High → 2**

---

## 🧹 Data Preprocessing

- Dropped identifier column (`Student_ID`)
- Encoded the target variable (Low/Moderate/High → 0/1/2)
- No missing values found
- Outliers detected using IQR and clipped where necessary  
  *(Physical Activity extreme values clipped to 0-8 hours)*
- Feature distributions reviewed using histograms + KDE

---

## 🔍 Exploratory Data Analysis (EDA)

### **Summary Statistics Highlights**
- Students study **7.47 hrs/day** on average  
- Sleep averages **7.50 hrs/day**  
- Physical activity ranges widely (**0 to 13 hours**)  
- GPA has a healthy distribution around **3.11**

### **Stress-Level Class Distribution**
- **High:** 1029  
- **Moderate:** 674  
- **Low:** 297  
➡️ *Highly imbalanced classes detected.*

### **Correlation Insights**
- Study hours and GPA correlate positively with stress  
- Sleep hours reduce stress  
- Physical activity mildly lowers stress  
- Extracurricular hours have little effect

### **Group Means by Stress Level**

| Feature | Low | Moderate | High |
|--------|------|-----------|-------|
| Study Hours | 5.47 | 6.97 | 8.38 |
| Sleep Hours | 8.06 | 7.94 | 7.04 |
| GPA | 2.82 | 3.03 | 3.26 |

➡️ *High-stress students study more, sleep less, and maintain a higher GPA.*

---

## 🤖 Classification Models

Three classification algorithms were explored:

### ✔ Logistic Regression
- Strong baseline model
- Uses class weighting to handle imbalance
- **Accuracy: 85%**

### ✔ Random Forest (with class weights)
- Learns nonlinear relationships
- Validated with cross-validation → **1.00 mean accuracy**
- No signs of overfitting due to stable cross-validation results

### ✔ CatBoost Classifier (class-weighted)
- Best model on the dataset
- Handles imbalance without SMOTE
- Fast and interpretable gradient-boosting method

---

## 🔑 Feature Importance Insights

### **Top Predictors of Stress**
1. Study Hours Per Day  
2. Sleep Hours Per Day  
3. GPA  
4. Physical Activity Hours  
5. Social Hours  

### **Least Important Features**
- Extracurricular Hours  

---

## 🖥️ Interactive Stress Prediction App (Gradio)

A GUI-based Gradio app lets users enter lifestyle values and receive a stress prediction.

### **Run the App**

```bash
pip install gradio
```

## 🧪 How to Run the Project
1️⃣ Clone the Repository
```bash
git clone https://github.com/<YourUsername>/StudentLifestyle-Stress-Level-Classification.git
cd StudentLifestyle-Stress-Level-Classification
```
2️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```
3️⃣ Open & Run Notebook
```bash
Student_Stress_Classification.ipynb
```
4️⃣ Launch the Gradio App
```bash
stress_app.launch()
```
## 🚀 Future Enhancements

- Add clustering (student lifestyle segmentation)

- Apply dimensionality reduction (PCA / t-SNE)

- Deploy Gradio app on HuggingFace Spaces

- Add Explainable AI (SHAP)
- Build full dashboard (Streamlit / PowerBI)

## 👩🏽‍💻 Author
**Hermela Seltanu Gizaw**

BSc. Data Science & Analytics, USIU-Africa

Mastercard Foundation Scholar
