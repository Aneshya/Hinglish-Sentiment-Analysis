# Code-Mix Sentiment Analysis on Hinglish Tweets

## 📌 Overview

This project presents a Transformer-based approach for **sentiment analysis of Hinglish (Hindi-English code-mixed) tweets**. Hinglish is widely used on social media platforms and poses unique challenges due to code-switching, transliteration variations, informal language, and inconsistent spelling patterns.

To address these challenges, we fine-tune **Multilingual BERT (mBERT)** for three-class sentiment classification: **Positive, Negative, and Neutral**.

---

## 🎯 Problem Statement

Traditional NLP models often struggle with Hinglish text because of:

- Code-mixing between Hindi and English
- Romanized Hindi words
- Informal grammar and spelling variations
- High frequency of out-of-vocabulary (OOV) words
- Noisy social media content

This project aims to build an accurate sentiment classification system capable of handling real-world Hinglish tweets.

---

## 📂 Dataset

### Hinglish-24k Dataset

A curated dataset containing **24,111 Hinglish tweets** collected by merging multiple publicly available sentiment analysis datasets.

### Class Distribution

| Sentiment | Tweets |
|------------|---------|
| Neutral | 8,987 |
| Positive | 7,940 |
| Negative | 7,184 |
| **Total** | **24,111** |

---

## ⚙️ Methodology

### 1. Data Preprocessing

The following preprocessing steps were applied:

- URL removal
- User mention removal
- Hashtag cleaning
- Emoji normalization
- Lowercasing
- Duplicate removal
- Noise filtering
- Stopword removal
- Dataset balancing

### 2. Tokenization

We utilized the **WordPiece Tokenizer** from mBERT to handle:

- Transliterated Hindi words
- Spelling variations
- Unknown vocabulary

Example:

```text
likhna → li ##kh ##na
```

### 3. Model Architecture

**Base Model:**
- `bert-base-multilingual-cased (mBERT)`

**Configuration:**

| Hyperparameter | Value |
|---------------|--------|
| Optimizer | AdamW |
| Learning Rate | 2e-5 |
| Epochs | 3 |
| Batch Size | 8 |
| Weight Decay | 0.01 |
| Warmup Steps | 500 |
| Max Sequence Length | 128 |

---

## 🧠 Model Pipeline

```text
Raw Hinglish Tweets
        │
        ▼
Data Cleaning & Preprocessing
        │
        ▼
WordPiece Tokenization
        │
        ▼
mBERT Encoder
        │
        ▼
Classification Head
        │
        ▼
Positive / Neutral / Negative
```

---

## 📊 Results

### Performance Comparison

| Model | Accuracy | Weighted Precision | Weighted Recall | Weighted F1 |
|---------|---------|---------|---------|---------|
| Naive Bayes + TF-IDF | 0.62 | 0.62 | 0.62 | 0.62 |
| SVM + TF-IDF | 0.65 | 0.65 | 0.65 | 0.65 |
| **mBERT (Proposed)** | **0.67** | **0.67** | **0.67** | **0.67** |

### Per-Class F1 Scores

| Class | F1 Score |
|---------|---------|
| Negative | 0.71 |
| Neutral | 0.60 |
| Positive | 0.70 |

### Key Findings

✅ mBERT outperformed traditional machine learning baselines.

✅ Subword tokenization effectively handled Hinglish spelling variations.

✅ Transformer-based models captured contextual information better than TF-IDF approaches.

---

## 🛠️ Tech Stack

### Languages

- Python

### Libraries

- Hugging Face Transformers
- PyTorch
- Scikit-learn
- NumPy
- Pandas
- NLTK

### Model

- Multilingual BERT (mBERT)

---

## 📁 Project Structure

```text
├── data/
│   ├── train.csv
│   ├── validation.csv
│   └── test.csv
│
├── notebooks/
│   └── training.ipynb
│
├── src/
│   ├── preprocessing.py
│   ├── train.py
│   ├── evaluate.py
│   └── inference.py
│
├── models/
│   └── fine_tuned_mbert/
│
├── requirements.txt
│
└── README.md
```

---

## 🚀 Applications

- Brand Monitoring
- Customer Feedback Analysis
- Social Media Analytics
- Opinion Mining
- Market Intelligence
- Multilingual NLP Systems

---

## 👥 Authors

- Aashi Garg
- Aneshya Das
- Arshi Arya
- Anushka Goyal
- Aditi

---

## 📄 Publication

**Code-Mix Sentiment Analysis on Hinglish Tweets**

Accepted at **NLPIR 2025 (Japan)**.

---

## 🔮 Future Work

- Explore XLM-RoBERTa and IndicBERT
- Sarcasm Detection
- Emotion Classification
- Aspect-Based Sentiment Analysis
- Real-time Social Media Monitoring Dashboard

---

## ⭐ Citation

```bibtex
@article{hinglish_sentiment_2025,
  title={Code-Mix Sentiment Analysis on Hinglish Tweets},
  author={Garg, Aashi and Das, Aneshya and Arya, Arshi and Goyal, Anushka and Aditi},
  year={2025}
}
```

---

### Repository Description

> Transformer-based Hinglish sentiment analysis using mBERT on a 24K+ tweet dataset, achieving 67% weighted F1-score and outperforming traditional TF-IDF based machine learning baselines.
