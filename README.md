# Coronavirus Tweet Sentiment Analysis

## Overview
The **Coronavirus Tweet Sentiment Analysis** project focuses on analyzing public sentiment expressed in tweets during the COVID-19 pandemic. By leveraging machine learning models, the project classifies sentiments as Positive, Neutral, or Negative, providing insights to policymakers, organizations, and businesses for informed decision-making and targeted communication strategies.

---

## Table of Contents
1. [Project Objective](#1-project-objective)
2. [Dataset Description](#2-dataset-description)
3. [Data Preprocessing](#3-data-preprocessing)
4. [Data Visualization](#4-data-visualization)
5. [Model Development](#5-model-development)
   - [Models Implemented](#51-models-implemented)
   - [Final Model Selection](#52-final-model-selection)
6. [Model Evaluation](#6-model-evaluation)
7. [Business Impact](#7-business-impact)
8. [Future Scope](#8-future-scope)
9. [Repository Structure](#9-repository-structure)
10. [How to Use](#10-how-to-use)

---

## 1. Project Objective
The project aims to:
- Classify COVID-19-related tweets into three sentiment categories: **Positive**, **Neutral**, and **Negative**.
- Provide actionable insights to:
  - Enable real-time monitoring of public sentiment.
  - Improve communication strategies and crisis management during the pandemic.

---

## 2. Dataset Description
- **Dataset Size**: 41,157 rows and 6 columns.
- **Columns**:
  - `UserName` and `ScreenName`: Encoded identifiers of users.
  - `Location`: Geographic origin (8,590 missing values handled).
  - `TweetAt`: Date of tweet.
  - `OriginalTweet`: Content of the tweet.
  - `Sentiment`: Target variable with five categories: `Extremely Positive`, `Positive`, `Neutral`, `Negative`, `Extremely Negative`.
- **Key Transformation**:
  - Sentiment categories were grouped into three broader classes:
    - `Positive` (combines `Extremely Positive` and `Positive`).
    - `Negative` (combines `Extremely Negative` and `Negative`).
    - `Neutral` remains as is.

---

## 3. Data Preprocessing
### 3.1 Data Cleaning
- Dropped unnecessary columns: `UserName`, `ScreenName`, `Location`, and `TweetAt`.
- Handled missing values in the `Location` column.

### 3.2 Text Preprocessing
- Expanded contractions (e.g., "don't" → "do not").
- Lowercased text for uniformity.
- Removed:
  - Punctuation and special characters.
  - URLs and digits.
  - Stopwords (e.g., "the", "and").
- Tokenized text into individual words.
- Normalized text for consistency.

---

## 4. Data Visualization
### 4.1 Sentiment Distribution
- Visualized the percentage distribution of Positive, Neutral, and Negative sentiments in the dataset.

### 4.2 Word Clouds
- Created word clouds to highlight frequently used terms for each sentiment category:
  - Positive: Words like "help" and "support."
  - Negative: Words like "lockdown" and "crisis."
  - Neutral: Words related to neutral operations (e.g., "price," "store").

### 4.3 Tweet Length Analysis
- Analyzed the distribution of tweet lengths across sentiments using violin plots to identify patterns in tweet verbosity.

---

## 5. Model Development

### 5.1 Models Implemented
1. **LSTM RNN**:
   - Achieved a validation accuracy of **67%**, but performance declined due to overfitting.
2. **TF-IDF Vectorization with Machine Learning Models**:
   - **Logistic Regression**: Best accuracy at **74.3%**.
   - **SVM**: Accuracy of **73.8%**.
   - **Random Forest**: Accuracy of **68.6%**.
   - **Naive Bayes**: Accuracy of **63.2%**.
3. **Word2Vec & Avg_Word2Vec with Machine Learning Models**:
   - Average accuracy across models: **57%**.

### 5.2 Final Model Selection
- **Chosen Model**: TF-IDF Vectorization with Logistic Regression.
- **Reasons**:
  - Highest accuracy (**74.3%**).
  - Balanced performance across all sentiment categories.
  - Scalability and efficiency for real-time sentiment monitoring.
  - Interpretability for identifying key influential terms in sentiment classification.

---

## 6. Model Evaluation
### 6.1 Metrics Used
- **Accuracy**: Overall correctness of predictions.
- **Precision**: Proportion of correctly identified Positive/Negative tweets.
- **Recall**: Ability to capture all actual Positive/Negative tweets.
- **F1-Score**: Harmonic mean of precision and recall for imbalanced datasets.
- **Confusion Matrix**: Analyzed misclassifications to identify improvement areas.

### 6.2 Results
- Positive and Negative sentiments achieved high precision and recall, ensuring accurate insights for business applications.
- Neutral sentiments had lower recall, indicating room for improvement in handling ambiguous tweets.

---

## 7. Business Impact
### 7.1 Real-Time Sentiment Monitoring
- Organizations can track public sentiment trends dynamically to anticipate public reactions and plan responses.

### 7.2 Crisis Management
- Negative sentiment detection aids in addressing public concerns promptly and improving stakeholder trust.

### 7.3 Targeted Communication
- Positive sentiment identification helps organizations capitalize on goodwill through marketing campaigns.

### 7.4 Operational Insights
- Neutral tweets provide feedback on operational aspects like pricing and service quality, guiding improvements.

---

## 8. Future Scope
- **Advanced Models**: Implement transformer-based models like BERT for enhanced accuracy and generalization.
- **Dataset Expansion**: Extend analysis beyond COVID-19 tweets for broader sentiment analysis use cases.
- **Sentiment Trend Analysis**: Incorporate time-series analysis to track changes in sentiment over time.

---

## 9. Repository Structure
├── notebook.ipynb # GoogleColab Notebook with complete analysis and model implementation. \
├── dataset.csv # Cleaned dataset used for training and testing. \
├── README.md # Documentation of the project. \
└── requirements.txt # List of dependencies for running the project.

## 10. How to Use

### Step 1: Clone the Repository
Clone the repository to your local machine using the following command:
```bash
git clone https://github.com/ImAbhijeetPanda/Coronavirus-Tweet-Sentiment-Analysis.git
```
---



Credits
This project is authored and maintained by **[Abhijeet Panda](https://github.com/ImAbhijeetPanda)**.

## Contact

For any questions or feedback, feel free to reach out:

- **Email**: [iamabhijeetpanda@gmail.com](mailto:iamabhijeetpanda@gmail.com)
- **LinkedIn**: [Abhijeet Panda](https://www.linkedin.com/in/imabhijeetpanda)
- **GitHub**: [ImAbhijeetPanda](https://github.com/ImAbhijeetPanda)



