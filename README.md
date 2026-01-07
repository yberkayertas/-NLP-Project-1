# Sentiment Analysis on Amazon Product Reviews

This project focuses on sentiment analysis of Amazon product reviews using both traditional machine learning models and transformer-based deep learning models. The main objective is to compare classical NLP approaches with modern transformer architectures in terms of accuracy and F1-score.

---

## Dataset Description

- Dataset: Amazon Product Reviews
- Total samples: ~568,000
- Source: Amazon Open Dataset
- Columns used:
  - Text: Review text
  - Score: Rating from 1 to 5

### Sentiment Label Mapping

The numeric review scores are mapped to sentiment labels as follows:

- Score 1–2 → Negative
- Score 3 → Neutral
- Score 4–5 → Positive

### Label Distribution

- Positive: 443,777
- Negative: 82,037
- Neutral: 42,640

The score is used as the ground truth label for sentiment classification.

---

## Environment Setup

Install the required libraries using the following command:

```bash
pip install -q transformers datasets scikit-learn pandas seaborn matplotlib tqdm


The project is designed to run on Google Colab with GPU support for transformer training.
---

# Data Preprocessing
Text Cleaning
*The following preprocessing steps are applied to the review text:
 Removal of URLs
 Removal of special characters
 Conversion to lowercase

def clean_text(text):
    text = re.sub(r"http\S+", "", text)
    text = re.sub(r"[^A-Za-z0-9(),!?\'\`]", " ", text)
    text = text.lower()
    return text.strip()
