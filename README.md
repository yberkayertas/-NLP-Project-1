# Amazon Product Reviews Sentiment Analysis

This project performs sentiment analysis on a large-scale dataset of 568,000 Amazon product reviews. It compares traditional Machine Learning approaches (Naive Bayes, Logistic Regression) with state-of-the-art Transformer-based models (DistilBERT).

## Dataset Overview
* **Source:** Amazon Fine Food Reviews
* **Size:** ~568,000 reviews
* **Features:** Text (Review body) and Score (1 to 5 stars)
* **Target Labels:** * **Positive:** 4-5 stars
    * **Neutral:** 3 stars
    * **Negative:** 1-2 stars

### Class Distribution
* Positive: 443,777
* Negative: 82,037
* Neutral: 42,640

## Project Workflow

### 1. Data Preprocessing
* Cleaned text by removing URLs and special characters.
* Converted all text to lowercase for consistency.
* Handled missing values.
* Split data into Train (80%), Validation (10%), and Test (10%) sets using stratified sampling to maintain class balance.

### 2. Methodology
The project implements three distinct modeling strategies:

* **Naive Bayes:** A baseline probabilistic classifier using TF-IDF vectorization (unigrams and bigrams).
* **Logistic Regression:** A linear model optimized with balanced class weights to handle the dataset's inherent class imbalance.
* **DistilBERT:** A small, fast, and light Transformer model based on the BERT architecture, fine-tuned specifically for this multi-class classification task.



## Performance Comparison

| Model | Accuracy | F1-Score (Macro) |
| :--- | :---: | :---: |
| Naive Bayes | ~0.86 | ~0.61 |
| Logistic Regression | ~0.86 | ~0.74 |
| **DistilBERT** | **~0.92** | **~0.80** |



## Installation & Usage

### Requirements
Ensure you have the following libraries installed:
```bash
pip install transformers datasets scikit-learn pandas seaborn matplotlib tqdm
