# Task 4: SMS Spam Detection System

## 🎯 Project Objective
The objective was to engineer a robust Natural Language Processing (NLP) pipeline to classify SMS messages as either "Spam" or "Ham" (legitimate). The project focused on transforming raw, unstructured text into a mathematical representation that a machine learning model could interpret with high confidence.

## 🗄️ Text Engineering & Vectorization
Sourcing and preparing text data is the most critical phase of this task. I focused on converting human language into numerical vectors that capture the importance of specific terms.

**The Pipeline:**
* **Cleaning:** Stripping irrelevant characters and normalizing the text corpus.
* **TF-IDF Vectorization:** Implemented the TfidfVectorizer (Term Frequency-Inverse Document Frequency). This ensures that common words like "the" or "is" are weighted less, while high-intent words (e.g., "win," "free," "urgent") are given higher priority.

## 🧠 Model Selection
I chose the Multinomial Naive Bayes (NB) algorithm for the classification layer.

* **Why Naive Bayes?** It is exceptionally efficient for text classification because it calculates the probability of a message being spam based on the frequency of the words it contains. It performs remarkably well even with smaller datasets and high-dimensional feature spaces.
* **Evaluation:** Used heatmaps to visualize the confusion matrix, ensuring that the model maintains a low rate of "false positives" (marking legitimate messages as spam).

## 🛠️ Technologies Used
* **NLP Tools:** Scikit-Learn (TfidfVectorizer)
* **Machine Learning:** Multinomial Naive Bayes
* **Data Management:** Pandas
* **Visualization:** Seaborn (Confusion Matrix Heatmaps)

## 🚀 Usage
The notebook allows for a streamlined workflow: load the message dataset, vectorize the text content, train the Naive Bayes engine, and immediately output a detailed classification report with accuracy metrics.