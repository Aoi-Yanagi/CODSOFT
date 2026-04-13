# Task 2: Credit Card Fraud Detection

## 🎯 Project Objective
The goal of this project was to develop a high-precision anomaly detection system capable of identifying fraudulent credit card transactions. Given the extreme rarity of fraud compared to legitimate transactions, the project focused on building a model that minimizes false negatives without overwhelming the system with false alarms.

## 🗄️ Dataset & Processing
The analysis was performed on a massive dataset containing over 1.8 million transaction records. Handling data at this scale required efficient preprocessing to ensure model stability.

**Key Processing Steps:**
* **Data Partitioning:** Segmented the data into 1,296,675 training rows and 555,719 testing rows to ensure the model could generalize to unseen financial patterns.
* **Feature Selection:** Identified and isolated numerical features that showed the highest variance between legitimate and fraudulent behavior.
* **Class Imbalance Management:** Addressed the inherent skewness of fraud data to prevent the model from simply "guessing" the majority class.

## 🧠 Technical Approach & Architecture
I implemented a Random Forest Classifier as the backbone of the detection engine. This ensemble approach was chosen for its ability to handle non-linear relationships and its inherent resistance to overfitting on noisy data.

* **Mechanism:** The model constructs an ensemble of decision trees, where each tree votes on the transaction's status. This "wisdom of the crowd" approach significantly reduces the variance found in single-tree models.
* **Feature Importance Logic:** Beyond simple classification, the engine calculates importance scores to rank features. This allows for a transparent look into why a transaction was flagged (e.g., specific spending thresholds or geographic anomalies).

## 🛠️ Technologies Used
* **Languages:** Python
* **Data Science:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn (RandomForestClassifier)
* **Visualization:** Seaborn, Matplotlib

## 🚀 Key Results
The final model identifies the "Top 10 Biggest Indicators of Fraud," providing a visual roadmap of risk factors. Performance was validated using confusion matrices and precision-recall curves to ensure reliability in a real-world financial environment.