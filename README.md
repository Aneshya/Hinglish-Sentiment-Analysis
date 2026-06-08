# Hinglish-Sentiment-Analysis

Overview

This project focuses on sentiment analysis of Hinglish (Hindi-English code-mixed) tweets, a challenging NLP task due to transliteration variations, informal language, and mixed linguistic structures. The goal is to classify tweets into Positive, Negative, and Neutral sentiment categories using a fine-tuned Multilingual BERT (mBERT) model.

Problem Statement

Traditional sentiment analysis models often struggle with code-mixed languages like Hinglish because of:

Non-standard grammar and spelling variations
Romanized Hindi words
Frequent code-switching between Hindi and English
High occurrence of out-of-vocabulary terms

This project addresses these challenges using Transformer-based multilingual language models.

Dataset

Hinglish-24k Dataset

Total Tweets: 24,111
Classes:
Positive
Negative
Neutral
Created by merging publicly available Hinglish sentiment datasets and harmonizing their labels into a unified classification scheme.
Methodology
Data Preprocessing
URL, hashtag, and mention removal
Emoji and emoticon normalization
Lowercasing and text normalization
Duplicate and noise removal
Dataset balancing and validation split preparation
Tokenization
WordPiece Tokenizer from bert-base-multilingual-cased
Maximum sequence length: 128
Handles transliterated Hindi and spelling variations effectively
Model
mBERT (Multilingual BERT)
Fine-tuned for 3-class sentiment classification
Optimizer: AdamW
Learning Rate: 2e-5
Epochs: 3
Batch Size: 8
Results
Model	Accuracy	Weighted F1
Naive Bayes + TF-IDF	~62%	~0.62
SVM + TF-IDF	~65%	~0.65
mBERT (Proposed)	67%	0.67

The fine-tuned mBERT model outperformed traditional machine learning baselines, demonstrating the effectiveness of Transformer architectures for code-mixed sentiment analysis.

Tech Stack
Python
Hugging Face Transformers
PyTorch
Scikit-learn
NumPy
Pandas
NLTK
Key Contributions
Curated the Hinglish-24k dataset from multiple public sources.
Implemented a complete NLP preprocessing pipeline.
Fine-tuned mBERT for sentiment classification.
Benchmarked Transformer-based models against traditional ML baselines.
Conducted performance evaluation and error analysis.
Applications
Brand Monitoring
Social Media Analytics
Customer Feedback Analysis
Opinion Mining
Multilingual NLP Research
Publication

Code-Mix Sentiment Analysis on Hinglish Tweets
Accepted at NLPIR 2025 (Japan).
