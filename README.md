
# 🛍️ Ecommerce Customer Spending Analysis Using Linear Regression

## Overview

This project aims to help a New York-based fashion ecommerce company decide where to invest development resources — in their **mobile app** or their **website** — by analyzing customer behavior and spending habits. The company provides in-store personal stylist consultations, and customers often make purchases later using either the mobile app or the website. 

Using exploratory data analysis (EDA) and machine learning, specifically **Linear Regression**, this project determines which platform influences higher yearly spending, guiding strategic business decisions.

---

## 🧠 Business Problem

The company wants to answer a simple but crucial question:

> **Should we improve the mobile app or the website to increase customer spending?**

Although both platforms are used to place orders, it’s unclear which platform leads to greater customer purchases. By analyzing behavioral data like time spent on each platform and other engagement metrics, we can uncover patterns and identify which touchpoint contributes more significantly to annual revenue.

---

## 📂 Dataset Description

This is a synthetic dataset provided for the project and contains the following features:

| Column Name           | Description                                                                 |
|-----------------------|-----------------------------------------------------------------------------|
| `Avg. Session Length` | Average session duration across platforms                                   |
| `Time on App`         | Average time spent using the mobile application                             |
| `Time on Website`     | Average time spent using the website                                        |
| `Length of Membership`| Duration of the customer’s membership with the service                      |
| `Yearly Amount Spent` | **Target variable** — Total dollars spent by the customer in one year       |

This dataset is assumed to be clean, with no missing or malformed data.

---

## 🔍 Exploratory Data Analysis (EDA)

To understand the relationships between variables, the following visualizations were created using **Seaborn** and **Matplotlib**:

1. **Jointplots**:
   - Compared `Time on Website` vs `Yearly Amount Spent`: Weak correlation.
   - Compared `Time on App` vs `Yearly Amount Spent`: Stronger positive correlation.

2. **Hexbin Plot**:
   - Showed `Time on App` vs `Length of Membership`: Revealed clustering behavior.

3. **Pairplot**:
   - Suggested `Length of Membership` and `Time on App` are the best indicators of yearly spending.

4. **Linear Model Plot**:
   - Visual regression line confirmed a strong linear relationship between `Length of Membership` and `Yearly Amount Spent`.

### ➕ Correlation Matrix
A heatmap showed the numeric correlation between all features, reinforcing the visual observations. Notably:
- `Length of Membership` and `Time on App` have the highest positive correlation with spending.

---

## 🧠 Model: Linear Regression

### Why Linear Regression?
Linear Regression is ideal for this task because we're predicting a **continuous numerical value** (Yearly Amount Spent) based on several independent numerical variables.

### Model Workflow:
1. **Feature Selection**:
   - Selected features: `Avg. Session Length`, `Time on App`, `Time on Website`, `Length of Membership`
   - Target: `Yearly Amount Spent`

2. **Train/Test Split**:
   - 70% training set
   - 30% test set
   - `random_state=101` for reproducibility

3. **Model Training**:
   - `LinearRegression()` from `sklearn.linear_model` was used.
   - Fitted to the training data.

4. **Model Coefficients**:
   | Feature               | Coefficient |
   |-----------------------|-------------|
   | Avg. Session Length   | ~26.0       |
   | Time on App           | ~38.0       |
   | Time on Website       | ~0.5        |
   | Length of Membership  | ~61.3       |

   - **Interpretation**: A unit increase in `Length of Membership` increases spending by $61 on average, assuming other features are constant.

---

## 🧪 Model Evaluation

The model was evaluated using the following metrics:

| Metric | Description | Value |
|--------|-------------|-------|
| MAE (Mean Absolute Error) | Average absolute difference between predicted and actual values | ~7.23 |
| MSE (Mean Squared Error)  | Average squared difference | ~79.81 |
| RMSE (Root MSE)           | Square root of MSE, measures spread of error | ~8.93 |

### Residual Analysis:
- A distribution plot of the residuals showed a roughly normal shape, indicating:
  - **No major outliers**
  - **Homoscedasticity (equal variance)**
  - **No skewed bias**

This validates the **assumptions of linear regression**.

---

## 📊 Results and Interpretation

### Insights:
- **Length of Membership** and **Time on App** are the strongest predictors of yearly customer spending.
- **Time on Website** has negligible impact on annual spending.

### Final Recommendation:
> 💡 **Focus on enhancing the mobile app experience.**

Increasing user engagement and satisfaction with the mobile app will likely yield higher returns in customer spending compared to investing in the website.

---

## 📁 Project Files

- `Linear Regression.ipynb` — Complete code and visualizations
- `README.md` — Project documentation

---

## 🧰 Tools and Technologies

- **Python 3**
- **Pandas & NumPy** for data wrangling
- **Matplotlib & Seaborn** for data visualization
- **scikit-learn** for machine learning model

---

## 🚀 Future Work

To build on this project:

1. **Model Enhancement**:
   - Try non-linear models: Random Forest, Gradient Boosting, or Polynomial Regression.
   - Tune hyperparameters and validate using cross-validation.

2. **Business Segmentation**:
   - Cluster customers based on usage and spending behavior for targeted marketing.

3. **Feature Expansion**:
   - Include demographic features: age, gender, income
   - Session-specific data: app features used, purchase funnel data

4. **A/B Testing**:
   - Test improvements on app vs website with real users.

---

## 👤 Author

**[Your Name]**  
Contract Data Scientist — Ecommerce & Retail Analytics  
📍 New York City  
📫 [your.email@example.com]  
🔗 [LinkedIn Profile](https://www.linkedin.com)

---

## 📜 License

This project is for educational and demonstration purposes only. The dataset is synthetic and does not contain any real customer data.

