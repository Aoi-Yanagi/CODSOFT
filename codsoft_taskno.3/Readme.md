# Task 3: Customer Churn Prediction

## 🎯 Project Objective
This project aims to predict customer attrition—commonly known as "churn"—for service-based businesses. By identifying users at risk of leaving, companies can implement targeted retention strategies. The focus was on building a predictive engine that balances sensitivity to churners with overall accuracy.

## 🧠 Technical Approach & Architecture
To achieve high predictive power, I utilized Gradient Boosting, a powerful boosting technique that builds the model sequentially.

* **Sequential Learning:** Unlike parallel methods, this model learns from the errors of previous iterations, refining its decision boundaries with each step to better capture the subtle characteristics of churn-prone customers.
* **Feature Optimization:**
  * **Standardization:** Applied StandardScaler to ensure features like "Tenure" and "Monthly Charges" were on a comparable scale, preventing any single variable from dominating the gradient updates.
  * **Categorical Encoding:** Transformed qualitative customer data into numerical formats suitable for mathematical optimization.

## 📊 Evaluation & Diagnostics
The model was evaluated on a hidden test set to verify its real-world utility.

* **Optimization:** Fine-tuned the classifier to achieve a high accuracy score while maintaining a detailed classification report across both classes (Stayed vs. Churned).
* **Visualization:** Developed a "Final Optimized Confusion Matrix" to map the AI’s predictions against actual outcomes, specifically tracking the trade-off between "Predicted Churn" and "Actual Churn."

## 🛠️ Technologies Used
* **Framework:** Scikit-Learn
* **Algorithms:** Gradient Boosting Classifier
* **Preprocessing:** Standard Scaling, Label Encoding
* **Analytics Tools:** Pandas, Seaborn for heatmap diagnostics