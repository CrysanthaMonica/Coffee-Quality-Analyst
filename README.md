# Coffee Quality Measures Prediction

## Overview
This project aims to analyze the quality of Arabica coffee beans, with a focus on identifying factors that influence the **aftertaste** of coffee. Using a dataset from Kaggle, which includes detailed attributes of coffee beans from around the world, this project specifically highlights coffee produced in **Ethiopia** and builds a predictive model to understand the relationships between various quality measures and the aftertaste score.

## Table of Contents
- [Project Motivation](#project-motivation)
- [Dataset](#dataset)
- [Objectives](#objectives)
- [Analysis Workflow](#analysis-workflow)
- [Modeling](#modeling)
- [Results and Findings](#results-and-findings)
- [Further Improvements](#further-improvements)
  
## Project Motivation
The quality of coffee beans is influenced by various factors such as acidity, flavor, balance, and sweetness. This project attempts to predict how these attributes influence a coffee's **aftertaste**, particularly in Arabica coffee from Ethiopia. The results can help coffee producers and consumers alike in understanding what makes a good coffee aftertaste and how to improve the quality of coffee beans.

## Dataset
- **Source**: [Kaggle Coffee Quality Database](https://www.kaggle.com/datasets/volpatto/coffee-quality-database-from-cqi)
- **Rows**: 1311
- **Attributes**: 44 features, including country of origin, bean variety, and quality scores (e.g., flavor, acidity, aftertaste)

### Key Features:
1. **Acidity**: A quality measure that evaluates the sharpness or tang of the coffee.
2. **Flavor**: The overall taste impression.
3. **Balance**: How well the components of the coffee harmonize.
4. **Aftertaste**: The taste that lingers after swallowing, which is the target variable in this project.
5. **Sweetness**: The presence of sweet flavors.

## Objectives
1. **Data Quality Assessment**: Review the dataset for inconsistencies, missing values, and overall structure.
2. **Preprocessing**: Clean the data and prepare it for modeling.
3. **Data Exploration**: Visualize key variables and their distributions.
4. **Model Development**: Build a predictive model to forecast the **aftertaste** score based on other coffee attributes.
5. **Model Evaluation**: Assess the accuracy and effectiveness of the chosen model.

## Analysis Workflow

### 1. Data Exploration
- The dataset was explored using **R** to understand its structure and distribution.
- Key variables such as **Country of Origin**, **Variety**, and **quality measures** (Acidity, Flavor, Aftertaste) were analyzed.

### 2. Data Cleaning
- Missing values were handled using **mean imputation** for numerical columns.
- Unnamed columns and irrelevant variables (those with zero variance) were removed to simplify the analysis.

### 3. Data Visualization
- **Barplots**: Generated for variables like country of origin and coffee variety, showing which countries produce the best-rated coffees.
- **Correlation Heatmaps**: Highlighted the relationships between different coffee attributes (such as acidity, flavor, and aftertaste) for Ethiopian coffee beans.

### 4. Modeling
- **Model Used**: Multiple Linear Regression.
- **Target Variable**: Aftertaste score.
- **Key Predictors**:
   - Acidity
   - Balance
   - Flavor

## Results and Findings
- **Acidity**, **balance**, and **flavor** were found to be positively correlated with a coffee's **aftertaste**.
- Interestingly, **sweetness** had a negative impact on the aftertaste, suggesting that sweeter coffee might not always result in a better lingering flavor.
- Ethiopia's coffee was generally highly rated for acidity but had room for improvement in terms of aftertaste.

| Predictor | Coefficient | P-value |
|-----------|-------------|---------|
| Acidity   | +0.34       | 0.001   |
| Balance   | +0.29       | 0.004   |
| Flavor    | +0.45       | <0.001  |
| Sweetness | -0.12       | 0.032   |

## Further Improvements
### 1. **Handling Data Imbalance**
   - The dataset may contain **class imbalance** regarding coffee scores, where certain quality measures like **flavor** might dominate the dataset while others are under-represented. Applying techniques like **SMOTE** (Synthetic Minority Over-sampling Technique) could help balance the data, especially for low-frequency attributes.
   
### 2. **Feature Engineering**
   - Additional features such as **altitude** or **harvest time** could be derived from the existing data to better explain variations in coffee quality. For instance, combining origin and variety into a single feature (interaction terms) could yield more meaningful insights.
   
### 3. **Advanced Modeling**
   - While linear regression was chosen for simplicity, trying more sophisticated models like **Random Forests**, **Gradient Boosting**, or **Support Vector Machines (SVM)** could yield better results in capturing non-linear relationships between the variables.
   
### 4. **Hyperparameter Tuning**
   - For future iterations, applying **hyperparameter optimization** techniques like **Grid Search** or **Random Search** could improve model accuracy and help avoid overfitting.
   
### 5. **Cross-validation**
   - Implementing **k-fold cross-validation** would provide a more robust estimate of model performance by ensuring that the model generalizes well across different subsets of the data.
   
### 6. **Expanding Data Sources**
   - Expanding the dataset to include **more countries** or **regions** beyond Ethiopia would increase model generalization and provide broader insights into Arabica coffee's global quality.
