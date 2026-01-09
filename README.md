# Spanish POS Tagging and NER Comparison
This project demonstrates the implementation and evaluation of various Natural Language Processing (NLP) techniques for Part-of-Speech (POS) Tagging and Named Entity Recognition (NER) using the Spanish CoNLL-2002 dataset.

File Name: project2 (1).ipynb

# Dataset Overview
The project utilizes the CoNLL-2002 dataset via nltk. This dataset is specifically designed for language-independent NER tasks, focusing on Spanish and Dutch. For this project, the Spanish portion (esp.train and esp.testa) was used.

Train Set Size: 8,323 sentences

Test Set Size: 1,915 sentences

# Methodologies
The project is divided into two primary NLP tasks:

# 1. Part-of-Speech (POS) Tagging
Four different statistical and machine learning approaches were implemented to assign grammatical categories to words:

Unigram Tagger: A baseline model that assigns the most frequent tag to a token based on training data.

HMM (Hidden Markov Model): A generative model that considers the probability of a tag sequence based on state transitions.

Bigram Tagger: An extension of the n-gram approach that considers the previous word's tag for context, utilizing a Unigram backoff.

Perceptron Tagger: A discriminative model that uses a structured perceptron algorithm to learn weights for features.

# 2. Named Entity Recognition (NER)
Three sophisticated architectures were compared for identifying entities (Location, Person, Organization, Misc):

CRF (Conditional Random Fields): A statistical modeling method that focuses on the relationship between labels in a sequence using handcrafted features (suffix, prefix, capitalization, etc.).

BERT (Transformer): Utilizes the bert-spanish-cased-finetuned-ner model for high-accuracy contextual embeddings.

SpaCy (CNN): A production-ready pipeline using a Convolutional Neural Network architecture.

# Key Findings & Performance

# POS Tagging Performance
In the POS tagging task, the Perceptron model outperformed all other statistical methods, showing the strength of discriminative learning.

Perceptron: 95.51% Accuracy | 95.44% F1 Score

Bigram (Context): 91.76% Accuracy | 91.46% F1 Score

HMM: 90.27% Accuracy | 90.23% F1 Score

Unigram (Baseline): 90.28% Accuracy | 89.72% F1 Score

# NER Performance
For the NER task, while BERT reached the highest raw accuracy, SpaCy maintained a more balanced F1 Score across the entity classes.

BERT (Transformer): 96.16% Accuracy | 80.64% F1 Score

CRF: 95.69% Accuracy | 73.93% F1 Score

SpaCy (CNN): 84.22% Accuracy | 84.35% F1 Score

# Installation & Requirements
To run the notebook, ensure you have the following libraries installed:

pip install nltk sklearn sklearn-crfsuite spacy pandas torch transformers seqeval
python -m spacy download es_core_news_sm

# How to Use

Open project2 (1).ipynb in Jupyter Notebook or Google Colab.

Run the Dataset & Preprocessing section to download necessary NLTK corpora.

Execute the cells sequentially to train the taggers and view the evaluation metrics.

