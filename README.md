# Comment Category Prediction Challenge

**Machine Learning | Multi-Class Classification Project**

This repository contains my solution for the **Comment Category Prediction Challenge**, where the objective is to predict the internal category assigned to user-generated comments on an online discussion platform.

---

## 📋 Project Overview

Online platforms need to automatically categorize user comments for effective content moderation, routing, and user experience management. 

This competition provides a dataset with rich information including:
- Raw comment text
- User engagement metrics (upvotes & downvotes)
- Emoticon/symbol usage
- Internal system signals
- Sensitive topic indicators (race, religion, gender, disability)

The task is to build a model that can accurately predict one of **4 possible categories** assigned by the platform's internal system.

---

## 🗂️ Dataset Description

## 📥 Dataset

The dataset is very large (~26 GB). It is not stored in this repository.

### How to Download:
- Download the full dataset from **Kaggle**:  
https://www.kaggle.com/competitions/comment-category-prediction-challenge/data

### Files Included:
- `train.csv` — Training dataset with target variable
- `test.csv` — Test dataset (without labels)
- `sample_submission.csv` — Correct submission format
- 

### Important Columns:

- **`comment`** — The actual text content of the comment
- **`created_date`** — Timestamp when comment was posted
- **`post_id`** — Reference to the parent post/thread
- **`emoticon_1, emoticon_2, emoticon_3`** — Binary indicators for special symbol groups
- **`upvote`** — Number of positive reactions
- **`downvote`** — Number of negative reactions
- **`if_1, if_2`** — Hidden internal platform features
- **`race, religion, gender, disability`** — Binary flags for sensitive content detection
- **`label`** — **Target Variable** (4 classes)

---

## 🛠️ Technologies & Libraries Used

- **Programming Language**: Python 3
- **Data Analysis**: NumPy, Pandas
- **Machine Learning**: Scikit-learn, LightGBM
- **Visualization**: Matplotlib, Seaborn
- **Others**: Feature engineering, Text processing

---

## 🧠 Models Implemented

I implemented and compared three different machine learning models:

| Model                        | Macro F1 Score | Remarks                     |
|-----------------------------|----------------|-----------------------------|
| Logistic Regression         | **0.79**       | Strong baseline             |
| Support Vector Classifier   | **0.80**       | Good performance            |
| **LightGBM**                | **0.83**       | **Best Performing Model**   |

**Best Model**: **LightGBM** achieved the highest Macro F1 score of **0.83**.

---

## 📊 Methodology

1. **Exploratory Data Analysis (EDA)**
   - Analyzed class distribution
   - Studied text length, engagement patterns
   - Examined correlation between features

2. **Feature Engineering**
   - Text-based features (TF-IDF, word counts, etc.)
   - Temporal features from `created_date`
   - Interaction features (upvote/downvote ratios)
   - Sensitive topic combinations

3. **Model Development**
   - Baseline model with Logistic Regression
   - Advanced models with hyperparameter tuning
   - Ensemble considerations

4. **Evaluation**
   - Primary Metric: **Macro F1 Score**
   - Cross-validation for robust performance estimation

---

## 🚀 Results & Insights

- LightGBM significantly outperformed other models, showing its strength in handling tabular + engineered text features.
- Engagement metrics (`upvote`, `downvote`) and sensitive topic flags proved to be strong predictors.
- Text content combined with metadata gave better results than text-only models.

---

