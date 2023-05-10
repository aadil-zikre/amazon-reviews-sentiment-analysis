# amazon-reviews-sentiment-analysis
Detailed Analysis with Predictive Models for Sentiments applied to Amazon Reviews

---

## Directory Structure
```
- data
   |- clothing_shoes_jewelry sample.txt # Sample of data used throughout
- helper-utils
   |- embeddings.py         # functions to generate Bert and XLNet Embeddings. Can be used for anything that can be used with Autotokenizer and Automodel
   |- models.py             # Class to train and test BiLSTM Classifer which takes embedded vectors as input
- notebooks
   |- ELMO Embedding Processor for Airline Dataset.ipynb
   |- Naive Bayes Model for Polarity Detection.ipynb
   |- Sentiment Analyzer Comparing Bert, XLNet and Elmo Embeddings.ipynb
   |- Text Preprocessing and Exploratory Text Mining.ipynb
```   
---
 
## Notebook Contents
### 1. Text Preprocessing and Exploratory Text Mining

Preprocessing includes:
1. Tokenization
2. Lemmatization and Stemming
3. Stop Words Removal
4. Non Words Removal
5. Pos Tagging
6. Regex for n words before and after target word

Other Analyses include:
1. Zipfs Law Curve
2. Binary Collocation analysis- Frequency based and Pointwise Mutual Information Based
3. Trigram Collocation Analysis 

### 2. Naive Bayes Model for Polarity Detection

2 Naive Bayes Models with varied levels of text preprocessing. Training of Model done on Sentence Polarity Corpus Dataset by NLTK 

### 3. Sentiment Analyzer Comparing Bert, XLNet and Elmo Embeddings

As the name suggests, prime objective is to build a sentiment polarity predictor. I tried 3 context based embeddings, Bert, XLNet and Elmo. I also experimented with varying levels of processing of text to see their impact on model accuracy. 

General Process is as follows:
1. Text is processed ( stopword removal, lemmatization, etc)
2. Embedding are created
3. Embeddings are passed into a BiLSTM layer of 64 units for each LSTM 
4. The resulting vector is passed through 2 dense layers followed by a Final Dense Layer 
5. Prediction on Amazon Reviews Dataset
6. Comparison with Naive Bayes Results from previous notebook

Training Dataset : Training Dataset used in this notebook is Twitter Airline Sentiment Dataset from Kaggle 

### 4. ELMO Embedding Processor for Airline Dataset

As I found the process of getting ELMO embeddings very cumbersome (not as straightforward as HuggingFace's Bert and Xlnet implementations), I did this part in a separate notebook. Also note that the ELMO Embeddings are very large in size. 

## CONCLUSION 
*** SPOILER ALERT ***
BERT is the best Context Aware Embedding with basic preprocessing of text without lemmatization and without stop word removal.
