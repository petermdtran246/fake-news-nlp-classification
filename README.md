# Fake News Classification with NLP

This project presents an end-to-end Natural Language Processing (NLP) workflow
for distinguishing fake news from factual news articles. The focus is not only
on building a classifier, but on understanding how linguistic patterns,
preprocessing decisions, and model selection influence performance.

The notebook walks through the full lifecycle of an NLP project, from raw text
exploration to model evaluation, following practices commonly used in
production-oriented data science work.

---

## Project Overview

The objective of this project is to answer the following question:

**Can we reliably classify fake news using linguistic and textual patterns alone?**

To address this, the project explores:
- Linguistic differences between fake and factual news
- Topic structure and narrative framing
- Sentiment distribution across news types
- Performance of simple linear classifiers on cleaned text data

---

## Dataset

The dataset consists of news articles labeled as either **Fake News** or
**Factual News**, with the following fields:
- `title`
- `text`
- `date`
- `fake_or_factual`

The dataset is balanced, allowing fair comparison between the two classes.

---

## NLP Workflow

### 1. Exploratory Linguistic Analysis
- Part-of-Speech (POS) tagging
- Named Entity Recognition (NER)
- Token and POS frequency comparison
- Entity distribution analysis

These steps help identify stylistic and structural differences between fake and
factual articles before modeling.

---

### 2. Text Preprocessing
- Removal of publisher and location prefixes
- Lowercasing and punctuation removal
- Stopword removal
- Tokenization and lemmatization

Preprocessing is designed to reduce noise while preserving semantic meaning.

---

### 3. Topic Modeling
- **LDA (Latent Dirichlet Allocation)** with Bag-of-Words
- **LSA (Latent Semantic Analysis)** with TF-IDF

Coherence scores are used to select an appropriate number of topics.
LSA is explored to reduce topic overlap observed with LDA and to better capture
contrasting narratives.

---

### 4. Sentiment Analysis
- VADER sentiment scoring
- Comparison of sentiment distributions between fake and factual news

This step evaluates whether sentiment alone provides useful separation between
news types.

---

### 5. Classification
Text is vectorized using a **Bag-of-Words** representation and used to train
linear classifiers:

- **Logistic Regression** (baseline model)
- **Linear SVM (SGDClassifier)** for comparison

Logistic Regression achieves the strongest and most stable performance on the
held-out test set.

---

## Results

- Logistic Regression achieved approximately **90% accuracy**
- Performance was balanced across precision, recall, and F1-score
- Linear SVM performed slightly worse without additional hyperparameter tuning

These results highlight that well-preprocessed text combined with simple,
interpretable models can be highly effective for NLP classification tasks.

---

## Key Takeaways

- Data understanding and preprocessing have a greater impact than model
  complexity
- Linguistic and stylistic cues are strong signals in fake news detection
- Simple linear models remain strong baselines for text classification
- Iterative experimentation is essential in real-world NLP projects

---

## File Structure

