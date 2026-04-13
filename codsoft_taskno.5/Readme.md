# Task 5: Handwritten Text Generation

## 🎯 Project Objective
Implement a character-level Recurrent Neural Network (RNN) to generate handwritten-like text. The model is trained on a dataset of handwritten text examples to learn human writing patterns and generate entirely new, original text sequences.

## 🗄️ Dataset Acquisition & Sourcing
Sourcing the correct dataset for this task required investigative data engineering. The originally provided dataset link was archived and redirected to a general landing page. 

**The Sourcing Process:**
1. Searched on PapersWithCode(PWC) but was in archived section on Hugging Face.
2. Traced the original dataset references through the PapersWithCode (PWC) archives on Hugging Face.
3. Identified the root source as the **IAM Handwriting Database**.
4. Registered on the official [FKI IAM Database website](https://fki.tic.heia-fr.ch/databases/iam-handwriting-database) to acquire the raw, authenticated data.

**Files Used:**
* `ascii.tar` -> Specifically the `words.txt` corpus, which contains the exact human transcriptions of the handwritten pages.

> **Note for Reproducibility:** Due to GitHub's file size limits, only the `ascii.tar` file is hosted in this repository. To run this notebook, create a free account on the official IAM website, download `whole dataset`, and place it in your Google Drive or local workspace.

## 🧠 Technical Approach & Architecture
This project navigates the technical distinction between Natural Language Processing (content generation) and Computer Vision (visual generation) by combining a Deep RNN with programmatic rendering.

### 1. Sequence Learning (The RNN)
* **Architecture:** A deeply stacked Character-Level LSTM (Long Short-Term Memory) network.
* **Training:** The model ingested a massive corpus of over 300,000 characters from the IAM `words.txt` transcriptions.
* **Mechanism:** By using a sliding window of 40 characters, the model was trained to predict the 41st character. Over multiple epochs, it learned human spelling, grammatical structures, and the specific sequential patterns of the IAM writers.

### 2. Handwritten-Like Rendering
* Because a mathematical RNN outputs digital text characters (not 2D pixel arrays like a GAN), the visual requirement of the prompt ("handwritten-like text") was achieved via programmatic rendering.
* The AI-generated text string is processed through `matplotlib` using a custom, dynamically downloaded cursive font (`Pacifico`) to accurately simulate and present human handwriting.

## 🛠️ Technologies Used
* **Framework:** TensorFlow / Keras (Sequential API)
* **Layers:** LSTM, Dense (Softmax), Dropout
* **Data Processing:** NumPy, Python `urllib`
* **Visualization:** Matplotlib, Textwrap, Font Manager

## 🚀 How to Run the Project
1. Clone this repository.
2. Download the `ascii.tar` dataset from the IAM Database and extract `words.txt`from `xml section`.
3. Open `handwriting_generation.ipynb` in Google Colab (Recommended: enable T4 GPU) or a local Jupyter environment.
4. Update the dataset path in Cell 1 to point to your `ascii.tar` file or extracted `words.txt`.
5. Run all cells sequentially. The script will train the AI, automatically securely download the required cursive fonts, and generate the final handwritten image.