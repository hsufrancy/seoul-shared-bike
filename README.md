# 🚲 Seoul Shared Bike Usage Classification
This repository is for my final project in Machine Learning course at Seoul National University.

## **Project Overview**  
This project focuses on **classifying the demand for shared bikes in Seoul** based on historical weather conditions, time-related features, and external factors. The goal is to predict whether the **bike demand will be high or low**, enabling better resource allocation for the shared bike system.  

## **Motivation**  
As an exchange student in South Korea, I wanted to work on a project related to local social issues. I found similarities between Seoul’s bike-sharing system and Taiwan’s **Ubike**, where demand is often misestimated, leading to a shortage of available bikes at key locations. Inspired by this issue, I applied **logistic regression** to classify demand using the **Seoul Bike Sharing Demand Dataset** from the UCI Machine Learning Repository.  

## **Dataset**  
- **Source**: [Seoul Bike Sharing Demand Dataset - UCI](https://archive.ics.uci.edu/dataset/560/seoul+bike+sharing+demand)  
- **Instances**: 8,760 (hourly data)  
- **Features (14 variables)**:  
  - **Target Variable**: `Rented Bike Count` (transformed into high/low demand categories)  
  - **Time Features**: `Date`, `Hour`, `Seasons`, `Holiday`, `Functional Day`  
  - **Weather Features**: `Temperature`, `Humidity`, `Windspeed`, `Visibility`, `Dew Point Temperature`, `Solar Radiation`, `Rainfall`, `Snowfall`  

## **Methodology**  

### **Step 1: Data Preprocessing**  
- **Transform `Rented Bike Count` into a categorical variable**:  
  - Used the **75th percentile as a threshold** to classify demand into **High Demand (≥75th percentile) and Low Demand (<75th percentile)**.  
- **Removed irrelevant features**, such as `Date`.  
- **Converted categorical variables** (`Seasons`, `Holiday`) into dummy variables to avoid multicollinearity.  
- **Ensured data integrity** by keeping all 8,760 instances.  

### **Step 2: Splitting the Data**  
- **Training Set**: 60%  
- **Cross-Validation Set**: 20%  
- **Test Set**: 20%  
- Verified that all sets maintain the original data distribution.  

### **Step 3: Model Implementation – Logistic Regression**  
- Implemented **binary classification** to predict bike demand.  
- **Evaluated performance metrics**:  
  - **Accuracy**: 85.27%  
  - **Precision**: 84.99%  
  - **Recall**: 85.27%  
  - **F1-Score**: 85.10%  
- **Addressed convergence issues** by increasing the number of iterations and applying feature scaling.  

### **Step 4: Model Optimization & Regularization**  
- **Polynomial Features Regularization**:  
  - Improved **accuracy to 89.84%** by capturing non-linear relationships.  
- **L1 & L2 Regularization**:  
  - Compared performance to prevent overfitting.  
- **Feature Scaling Analysis**:  
  - Standardization led to small but consistent improvements in performance.  

### **Step 5: Cross-Validation & Generalization**  
- Applied **cross-validation** to ensure model stability and reliability.  
- Achieved an **average accuracy of 86.8% across folds**, with low variance.  

## **Key Findings & Insights**  
- **The 75th percentile threshold effectively differentiates high and low demand.**  
- **Polynomial features significantly improve model accuracy.**  
- **Feature scaling enhances convergence and performance stability.**  
- **Cross-validation confirms strong generalization capability.**  

## **Future Improvements**  
- **Test additional models**, such as Decision Trees or Neural Networks.  
- **Incorporate external data**, such as traffic congestion and public holidays.  
- **Implement a real-time prediction system** for bike allocation.  

## **How to Run the Project**  
### **Requirements**  
Install dependencies:  
```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```
### **Run the Jupyter Notebook**  
```bash
jupyter notebook Seoul_Bike_Classification.ipynb
```

## **Author**  
**Francy Hsu**  
