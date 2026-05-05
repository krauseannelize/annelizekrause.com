---
title: "Disaster Tweet Classification"
date: 2026-05-05
summary: "Binary classification pipeline that distinguishes real disaster tweets from casual ones, using TF-IDF features and machine learning baselines on a Kaggle dataset of 7,613 labelled tweets."
tags:
  - NLP
  - Machine Learning
  - Text Classification
  - TF-IDF
  - Binary Classification
tech_stack:
  - Python
  - scikit-learn
  - NLTK
  - Pandas
  - Jupyter
links:
  - type: github
    url: https://github.com/krauseannelize/nlp-disaster-tweets
    label: Code
  - type: video
    url: https://youtu.be/__iId3S_-5w
    label: Video Walkthrough
featured: true
status: "Masterschool"
role: "Solo Project"
---

A binary text classification pipeline that distinguishes real disaster-related tweets from casual ones using the [Kaggle Disaster Tweets dataset](https://www.kaggle.com/c/nlp-getting-started) of 7,613 pre-labelled posts. The workflow covers text preprocessing (lowercasing, URL/mention removal, stop-word removal, lemmatisation), feature extraction with TF-IDF, baseline comparison between **Logistic Regression** and **Linear SVC**, and hyperparameter tuning via GridSearchCV, reaching **83% accuracy** after tuning.

The project also includes an honest error analysis: the model handles explicit disaster keywords and factual, news-like language well, but struggles with figurative language, sarcasm, and short tweets where context is doing most of the work. This bag-of-words ceiling motivates the natural next step toward word embeddings or transformer-based models like BERTweet.

Built locally in VS Code as part of Masterschool's NLP module.
