# Analysis of Contributions to Type II Diabetes

This project explores the primary factors contributing to Type II Diabetes and investigates the relationship between food prices and nutritional quality.

## Project Overview

According to the CDC, Type II Diabetes is a major health crisis affecting about 1 in 10 Americans. [cite: 5] This project aims to identify the demographic and health indicators that are most predictive of diabetes. We then explore a related economic factor: whether the nutritional quality of a staple food, like bread, is correlated with its price. [cite: 13, 16]

### Research Questions
1.  What are the most significant risk factors for developing Type II Diabetes?
2.  Is there a demonstrable relationship between the price of bread and its nutritional content? [cite: 231]

---

## Methodology

This project is divided into two main analyses:

### 1. Predicting Diabetes Risk

To identify the key indicators of diabetes, we used data from the CDC's Behavioral Risk Factor Surveillance System (BRFSS). [cite: 41]

* **Models Used**: We employed both **Random Forest** and **Logistic Regression** algorithms. [cite: 78, 112]
* **Data Handling**: The initial dataset was highly imbalanced. [cite: 61] We performed **upsampling** on the minority class (individuals with diabetes) to create a balanced dataset, which significantly improved the predictive power of our Random Forest model. [cite: 66, 67]
* **Evaluation**: Models were evaluated using ROC curves and confusion matrices to compare their accuracy and resilience to errors. [cite: 214]

### 2. Analyzing Price vs. Nutritional Content

To study the link between price and nutrition, we web-scraped data for bread products from the grocery store Safeway. [cite: 234]

* **Model Used**: A **Linear Regression** model was built to predict price based on nutritional variables like calories, sugar, protein, and fiber. [cite: 242]
* **Model Refinement**: We used the **Variance Inflation Factor (VIF)** to address multicollinearity and removed variables with a VIF greater than 5 (e.g., Calories). [cite: 322, 323] We then used **BIC backward selection** to eliminate insignificant variables, resulting in the most optimal model. [cite: 403, 405]

---

## Key Findings

### Diabetes Prediction

The **Balanced Random Forest model** was the most effective predictor of diabetes, achieving an **AUC of 0.93**. [cite: 445] The top five most influential factors for predicting Type II Diabetes were:
* Body Mass Index (BMI) [cite: 443]
* Age [cite: 443]
* General Health (self-assessed) [cite: 443]
* High Blood Pressure [cite: 443]
* Income [cite: 443]

### Price vs. Nutrition

Our analysis did not find a simple, direct relationship between "healthy" food and price. [cite: 437] The final linear regression model showed that:
* **Dietary Fiber**, **Total Sugars**, and **Cholesterol** had a positive relationship with price. [cite: 435]
* **Protein** and **Calcium** had a negative relationship with price. [cite: 436]

The unexpected positive correlation between price and unhealthy indicators like sugar and cholesterol may be due to specialty or dessert-style bread products that cost more. [cite: 467, 469, 470] Ultimately, the model could not definitively conclude that more nutritious bread is consistently more expensive. [cite: 473]

## Data Sources
* California Behavioral Risk Factor Surveillance Survey (BRFSS) [cite: 19]
* CDC's Nationwide 2015 BRFSS survey data [cite: 41]
* Web-scraped data from Safeway.com [cite: 234]
