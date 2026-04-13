# Task 1: Movie Genre Classification 🎬

## 🎯 Project Objective
"Create a machine learning model that can predict the genre of a movie based on its plot summary or other textual information. You can use techniques like TF-IDF or word embeddings with classifiers such as Naive Bayes, Logistic Regression, or Support Vector Machines."

## 🗄️ Dataset Information
* **Source:** [Genre Classification Dataset IMDb (Kaggle)](https://www.kaggle.com/datasets/hijest/genre-classification-dataset-imdb)
* **Features Used:** `Plot Summary` (Input Text) and `Genre` (Target Label).
* **Description:** A collection of movie plot summaries mapped to their primary genres, used to train the model to understand the relationship between vocabulary and cinematic categories.

## 🧠 Technical Approach
This project frames genre prediction as a supervised multi-class text classification problem. Based on the project requirements, **TF-IDF** and **Logistic Regression** were selected as the primary architecture.

### 1. Natural Language Processing (Text Cleaning)
* Utilized Python's `re` (Regular Expressions) to clean the raw plot summaries by removing special characters, numbers, and unnecessary punctuation to reduce noise in the dataset.

### 2. Feature Engineering (TF-IDF)
* Transformed the raw text summaries into numerical vectors using Scikit-Learn's `TfidfVectorizer`. This highlights unique, genre-defining words (like "spaceship" for Sci-Fi) while penalizing generic terms (like "the", "and").

### 3. Classification Engine (Logistic Regression)
* Built a **Confident Logic Model** using `LogisticRegression(C=3.0, max_iter=2500)`. 
* The `C=3.0` hyperparameter was tuned to balance the model's confidence, and `max_iter=2500` ensures the algorithm fully converges on the complex text data without timing out.

## 📊 Evaluation & The "60% Accuracy Ceiling"
The final model successfully achieved an accuracy of **60.16%** on the testing data. In the context of this specific Kaggle dataset, this is a highly optimized and authentic result. 

**Why is ~60% the authentic ceiling for this dataset?**
1. **Inherent Multi-Genre Overlap:** Most movies span multiple genres (e.g., an Action-Comedy). This dataset forces a strict single-label classification. If the model predicts "Comedy" but the ground truth is strictly labeled "Action", it is penalized, artificially lowering the accuracy score.
2. **Subjective Ambiguity:** Text summaries often lack strict genre boundaries. A summary about a "heist" could equally be categorized as a Thriller, Action, or Crime movie.
3. **Class Imbalance:** The dataset is heavily weighted toward generic labels like "Drama" and "Documentary," making minority classes inherently difficult to predict without overfitting.

## 🛠️ Technologies Used
* **Language:** Python
* **Environment:** Jupyter Notebook (`movie_classification_workspace.ipynb`)
* **Data Handling:** `pandas`
* **NLP & Text Processing:** `re` (Regex), `TfidfVectorizer`
* **Machine Learning:** `scikit-learn` (`LogisticRegression`, `accuracy_score`, `classification_report`)

## 🚀 How to Run
1. Clone this repository.
2. Ensure you have the required libraries installed (`pip install pandas scikit-learn`).
3. Download the dataset from the Kaggle link provided above and place the text files in your project directory.
4. Open `movie_classification_workspace.ipynb` and run the cells sequentially to view the text cleaning process, model training, and the final classification report.