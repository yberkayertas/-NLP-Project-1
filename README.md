# Amazon Product Reviews Sentiment Analysis
This project aims to perform sentiment analysis on a large-scale dataset of 568,000 Amazon product reviews. The study compares multiple approaches, ranging from traditional machine learning algorithms to deep learning and transformer-based models, to classify consumer sentiment accurately.

The complete code and implementation details can be found in the notebook: RE_Project1_(Sentiment_Analysis_on_Amazon_Product_Reviews)(1).ipynb

# Project Overview
The core objective is to map product review text to three sentiment categories based on the user's score (1-5 scale):

Negative: 1-2 Stars

Neutral: 3 Stars

Positive: 4-5 Stars

The dataset is naturally imbalanced with a high volume of positive reviews. To address this, performance is evaluated using both Accuracy and F1-Score (macro average) to ensure the models perform reliably across all sentiment classes.

# Tech Stack and Libraries
Language: Python
Data Manipulation: Pandas, Numpy
Visualization: Matplotlib, Seaborn
Machine Learning: Scikit-learn (Naive Bayes, Logistic Regression, SVM, Random Forest)
Deep Learning: TensorFlow/Keras (CNN)
Transformer Models: Hugging Face Transformers (DistilBERT)

# Preprocessing Pipeline
The text data underwent the following cleaning steps before training:
URL removal via regex.
Removal of special characters and punctuation.
Conversion of text to lowercase.
Dataset splitting: 80% Training, 10% Validation, and 10% Testing (Stratified).

# Model Performance Results
Below are the accuracy and F1-score results achieved by each model during the validation phase:

# DistilBERT
Accuracy: 0.92
F1-Score: 0.80
Interpretation: Best overall performance; effectively captures contextual nuances.
# CNN (Convolutional Neural Network)
Accuracy: 0.92
F1-Score: 0.80
Interpretation: High performance via local pattern recognition in text sequences.
# SVM (Linear SVC)
Accuracy: 0.91
F1-Score: 0.78
Interpretation: The most effective traditional machine learning algorithm for this dataset.
# Logistic Regression
Accuracy: 0.86
F1-Score: 0.74
Interpretation: Balanced and efficient for large-scale text classification.
# Naive Bayes
Accuracy: 0.86
F1-Score: 0.61
Interpretation: Strong baseline but struggles with identifying neutral sentiment.
# Random Forest
Accuracy: 0.79
F1-Score: 0.37
Interpretation: Underperformed due to tree depth constraints on high-dimensional text data.

# Conclusions
Transformer-based models (DistilBERT) and Deep Learning (CNN) provided the highest accuracy, demonstrating the importance of capturing word order and context.
Traditional models like SVM performed surprisingly well and are significantly faster to train than neural networks.
The F1-Score across all models highlights the challenge of identifying "Neutral" reviews, which often contain mixed signals that are harder to classify than "Positive" or "Negative" ones.

# Usage
To reproduce the results:
Install requirements: pip install transformers datasets scikit-learn pandas seaborn matplotlib tqdm
Open RE_Project1_(Sentiment_Analysis_on_Amazon_Product_Reviews)(1).ipynb in a Jupyter or Google Colab environment.
Ensure the Amazon Reviews.csv file is accessible via the path specified in the data loading section.
Run the cells sequentially to perform preprocessing, training, and evaluation.

