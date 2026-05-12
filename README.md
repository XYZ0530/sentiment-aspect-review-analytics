# Sentiment Classification and Aspect-Based Review Analytics

This repository presents an individual NLP assignment focused on sentiment classification and aspect-based product review analytics. The project combines supervised sentiment models with topic and aspect extraction methods to support product review analysis and aspect-level product comparison.

## Project Overview

The project builds an NLP review analytics pipeline for product reviews. It compares classical machine learning and deep learning approaches for sentiment classification, then applies topic and aspect extraction methods to identify review themes that can support product comparison and ranking.

Core tasks:

- Clean and preprocess product review text.
- Train SVM sentiment classifiers using CountVectorizer and TF-IDF features.
- Train BiLSTM sentiment classifiers using CBOW and Skip-Gram Word2Vec representations.
- Apply LDA, BERTopic, and CorEx for topic/aspect discovery.
- Use aspect-level sentiment signals to support product review analytics.

## What is Aspect-Based Sentiment Analysis?

Aspect-Based Sentiment Analysis (ABSA) goes beyond overall positive or negative sentiment. Instead of only asking whether a review is positive, ABSA tries to identify what the review is about, such as print quality, ink cost, setup, speed, reliability, or support, and then connect sentiment to those specific aspects.

For product reviews, this is useful because two products may have similar overall ratings but different strengths and weaknesses across specific aspects.

## Dataset

The project uses product review text collected for an academic assignment, centered on Best Buy printer reviews.

The raw review dataset is not included in this portfolio repository because review text may be subject to data-sharing and copyright limitations. The notebooks expect review data in CSV format.

Expected review data format:

```text
product_url,product_name,review_text
```

The processed aspect notebook also uses a cleaned format similar to:

```text
product_url,product_name,review_text,Clean
```

## Methodology

1. Collect or load product review data.
2. Clean text by lowercasing, removing noise, normalizing emojis/contractions, and preparing tokens.
3. Build sentiment classification features using:
   - CountVectorizer
   - TF-IDF
   - CBOW Word2Vec
   - Skip-Gram Word2Vec
4. Train and evaluate sentiment classifiers.
5. Extract topics/aspects using LDA, BERTopic, and CorEx.
6. Combine aspect signals and sentiment predictions to support product-level comparison.

## Sentiment Classification Models

The sentiment classification task compares:

- SVM with CountVectorizer features
- SVM with TF-IDF features
- BiLSTM with CBOW embeddings
- BiLSTM with Skip-Gram embeddings

The best documented result is the BiLSTM with Skip-Gram representation.

## Aspect / Topic Extraction

The project explores multiple unsupervised or weakly supervised topic/aspect methods:

- LDA for probabilistic topic modeling
- BERTopic for transformer-assisted topic discovery
- CorEx for anchored aspect extraction

These methods are used to identify product review themes such as ease of use, print quality, ink cost, speed/noise, paper handling, reliability, and support.

## Results

| Model | Feature Representation | Accuracy | F1 Score |
|---|---|---:|---:|
| SVM | CountVectorizer | 86.42% | 0.8647 |
| SVM | TF-IDF | 89.67% | 0.8974 |
| BiLSTM | CBOW | 88.90% | 0.8922 |
| BiLSTM | Skip-Gram | 90.29% | 0.9034 |

Best result: **BiLSTM with Skip-Gram achieved 90.29% accuracy and 0.9034 F1**.

## Tech Stack

- Python
- pandas
- NumPy
- scikit-learn
- TensorFlow / Keras
- NLTK
- Gensim
- BERTopic
- CorEx
- spaCy
- TextBlob
- matplotlib
- seaborn
- Jupyter Notebook

## Repository Structure

```text
.
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   └── README.md
├── notebooks/
│   ├── 01_sentiment_classification.ipynb
│   └── 02_aspect_review_analytics.ipynb
├── results/
│   └── model_metrics.csv
├── sample_outputs/
│   ├── lda_topics.csv
│   └── bertopic_topic_keywords_sample.csv
└── src/
    └── README.md
```

## How to Run

Create and activate a virtual environment:

```bash
python -m venv .venv
.venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Some NLP components require additional language resources:

```bash
python -m spacy download en_core_web_sm
```

Open Jupyter Notebook:

```bash
jupyter notebook
```

Suggested notebook order:

1. `notebooks/01_sentiment_classification.ipynb`
2. `notebooks/02_aspect_review_analytics.ipynb`

Before running, place your review CSV in a local data folder and update notebook file paths as needed. Raw data and trained model artifacts are intentionally excluded from this portfolio repository.

## Limitations

- This is an academic individual assignment, not a production system.
- Raw review data and trained binary model files are not included.
- Results are based on the assignment setup and should not be generalized to all product review domains.
- The notebooks may require path updates before rerunning on a new machine.
- BERTopic, spaCy, and TensorFlow dependencies can be environment-sensitive.

## What I Learned

- How to compare classical ML and deep learning sentiment models.
- How text representation affects sentiment classification performance.
- How to train BiLSTM models using Word2Vec embeddings.
- How topic modeling and aspect extraction can support review analytics.
- How to communicate NLP results using both model metrics and business-facing product insights.

## Resume Summary

Built an individual NLP review analytics pipeline for product sentiment classification and aspect-based review analysis. Compared SVM models using CountVectorizer and TF-IDF with BiLSTM models using CBOW and Skip-Gram embeddings; best result was BiLSTM Skip-Gram with **90.29% accuracy** and **0.9034 F1**. Applied LDA, BERTopic, and CorEx to extract product review aspects for product comparison and ranking.
