# IMDB Movie Review Sentiment Analysis

A comparative Natural Language Processing (NLP) project that evaluates **classical machine learning** and **deep learning** approaches for binary sentiment classification on the **IMDB movie review dataset**.

The repository explores multiple text representation strategies and model families to measure how feature engineering and neural embeddings affect sentiment analysis performance.

## Overview

This project predicts whether an IMDB movie review is **positive** or **negative** using:

- **Classical ML models**
  - Logistic Regression
  - Support Vector Machine (SVM)
- **Deep learning models**
  - Bidirectional LSTM (Bi-LSTM)
  - Bidirectional GRU (Bi-GRU)

The experiments compare the following embeddings/features:

- **Bag-of-Words (BoW)**
- **TF-IDF**
- **Word2Vec**
- **GloVe**

## Objectives

- Build an end-to-end sentiment analysis workflow for movie reviews
- Compare sparse feature methods against dense word embeddings
- Benchmark traditional classifiers vs recurrent neural architectures
- Evaluate models using standard classification metrics

## Dataset

- **Dataset:** IMDB Movie Review Dataset
- **Classes:** Positive / Negative
- **Total samples:** 50,000 reviews
- **Train-test split:** 80:20

A local copy of the dataset is included as:

- `IMDB-Dataset.csv`

## Methodology

### 1) Classical Machine Learning

Classical models were trained on 300-dimensional text representations:

- **BoW (300 features)**
- **TF-IDF (300 features)**

Models:

- Logistic Regression
- SVM

### 2) Deep Learning

Recurrent neural models were trained with pretrained/distributed vector representations:

- **Word2Vec (300d)**
- **GloVe (300d)**

Models:

- Bi-LSTM
- Bi-GRU

### 3) Evaluation Metrics

Each experiment reports:

- Accuracy
- Precision
- Recall
- F1-score

## Results Summary

### Classical Machine Learning Results

| Model | Feature | Accuracy | Precision | Recall | F1-score |
|---|---|---:|---:|---:|---:|
| Logistic Regression | BoW | 0.8143 | 0.8049 | 0.8314 | 0.8179 |
| Logistic Regression | TF-IDF | 0.8148 | 0.8070 | 0.8292 | 0.8180 |
| SVM | BoW | 0.8137 | 0.8020 | 0.8348 | 0.8181 |
| SVM | TF-IDF | 0.8155 | 0.8062 | 0.8324 | 0.8191 |

### Deep Learning Results

| Model | Embedding | Accuracy | Precision | Recall | F1-score |
|---|---|---:|---:|---:|---:|
| Bi-LSTM | Word2Vec | 0.8969 | 0.8807 | 0.9192 | 0.8995 |
| Bi-LSTM | GloVe | 0.8436 | 0.8126 | 0.8947 | 0.8517 |
| Bi-GRU | Word2Vec | **0.8980** | **0.8809** | **0.9212** | **0.9006** |
| Bi-GRU | GloVe | 0.8609 | 0.8374 | 0.8971 | 0.8662 |

## Key Findings

- **Deep learning models significantly outperformed classical ML models** on this task.
- **Word2Vec-based recurrent models** performed better than their **GloVe-based** counterparts in these experiments.
- **Bi-GRU + Word2Vec** achieved the best overall performance:
  - Accuracy: **0.8980**
  - F1-score: **0.9006**
- Among the classical baselines, **SVM + TF-IDF** delivered the strongest result.

## Repository Structure

```text
NLP-Assignment/
├── IMDB-Dataset.csv
├── README.md
├── nlp-assignment.ipynb
├── logistic_regression_bow.ipynb
├── svm_tfidf.ipynb
├── bi_lstm_word2vec.ipynb
├── bi_gru_glove.ipynb
└── output.png
```

## Notebook Guide

- `nlp-assignment.ipynb`  
  Consolidated assignment notebook covering both classical and deep learning sections.

- `logistic_regression_bow.ipynb`  
  Logistic Regression experiments with BoW and TF-IDF features.

- `svm_tfidf.ipynb`  
  SVM experiments with BoW and TF-IDF features.

- `bi_lstm_word2vec.ipynb`  
  Bi-LSTM experiments using Word2Vec and GloVe embeddings.

- `bi_gru_glove.ipynb`  
  Bi-GRU experiments using Word2Vec and GloVe embeddings.

## Technologies Used

- Python
- Jupyter Notebook
- pandas
- NumPy
- scikit-learn
- TensorFlow / Keras
- NLTK
- Gensim
- Matplotlib

## How to Run

### 1) Clone the repository

```bash
git clone https://github.com/MahirAzmain/NLP-Assignment.git
cd NLP-Assignment
```

### 2) Install dependencies

Install the required libraries in your Python environment:

```bash
pip install pandas numpy scikit-learn tensorflow nltk gensim matplotlib gdown
```

### 3) Launch Jupyter Notebook

```bash
jupyter notebook
```

Then open any notebook and run the cells sequentially.


## Presentation Resources

- [Context_Over_Counting.pptx](https://github.com/user-attachments/files/26012864/Context_Over_Counting.pptx)
- [IMDB.pptx](https://github.com/user-attachments/files/26012863/IMDB.pptx)

## Conclusion

This repository presents a clear comparative study of sentiment analysis techniques on the IMDB dataset. The results show that while BoW/TF-IDF-based classical models provide solid baselines, recurrent neural networks with dense embeddings achieve substantially stronger performance, with **Bi-GRU + Word2Vec** emerging as the best-performing approach in this project.

---

If you found this project useful, consider starring the repository.
