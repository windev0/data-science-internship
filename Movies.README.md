# Movie Reviews Sentiment Analysis 🎬📊

## Project Overview

This project focuses on analyzing movie reviews using Natural Language Processing (NLP) techniques to automatically classify reviews as **positive** or **negative**.

The objective is to build a sentiment classification pipeline, starting from raw textual data, through data exploration and preprocessing, until the development and evaluation of a machine learning model capable of predicting the sentiment of new movie reviews.

This project was conducted as part of my Data Analysis learning journey with **AnalystData Lab**, with a focus on data understanding, cleaning, feature engineering, and machine learning interpretation.

---

# 1. Business Understanding

Before building a predictive model, the first step was to define the analytical objective.

The main question addressed in this project is:

> **Can we predict whether a movie review expresses a positive or negative sentiment based only on its text content?**

This problem can be considered a **binary text classification task**, where:

- Input: Movie review text
- Output: Sentiment category

The two possible outcomes are:

- `positive`
- `negative`

---

# 2. Dataset Understanding

## Dataset Description

The dataset contains movie reviews with their associated sentiment labels.

Each observation represents one user review.

Dataset structure:

| Column | Description | Data Type |
|---|---|---|
| review | Text content of the movie review | String |
| sentiment | Sentiment label (positive/negative) | String |

---

## Dataset Overview

Initial inspection was performed using:

- `shape()`
- `info()`
- `describe()`

Results:

- Total observations: **50,000 reviews**
- Number of features: **2**
- Missing values: **None**
- Data types: **String**

The dataset is therefore complete and ready for preprocessing.

---

# 3. Exploratory Data Analysis (EDA)

## Sentiment Distribution

The distribution of sentiments was analyzed to understand the balance between classes.

Results:

| Sentiment | Number of Reviews |
|---|---:|
| Positive | 24,884 |
| Negative | 24,698 |

Percentage distribution:

- Positive reviews: **50.2%**
- Negative reviews: **49.8%**

## Interpretation

The dataset is highly balanced, with almost the same proportion of positive and negative reviews.

This is important because a balanced dataset prevents the machine learning model from being biased toward one class.

No resampling techniques were required.

---

# 4. Text Data Preprocessing

Machine learning algorithms cannot directly process raw text.

Therefore, the reviews needed to be transformed into a structured numerical representation.

The preprocessing steps included:

## Text Cleaning

The following transformations were applied:

- Conversion to lowercase
- Removal of HTML tags
- Removal of unnecessary characters
- Removal of noise from text


Example:

Before:

```

"This movie was AMAZING!!! <br />"

```

After:

```

"this movie was amazing"

```

---

# 5. Feature Engineering: Text Vectorization

## TF-IDF Transformation

The cleaned text was converted into numerical features using **TF-IDF (Term Frequency - Inverse Document Frequency)**.

TF-IDF assigns importance scores to words based on:

- How frequently a word appears in a review
- How informative the word is compared to the entire dataset

Example:

Text:

```

"The movie was amazing"

```

is transformed into a numerical vector that can be understood by machine learning algorithms.

---

# 6. Dataset Splitting

The dataset was divided into two parts:

## Training Set

80% of the data was used to train the model.

Purpose:

- Learn patterns between words and sentiments


## Testing Set

20% of the data was used to evaluate performance.

Purpose:

- Measure how well the model performs on unseen reviews


Final split:

- Training data: **40,000 reviews**
- Testing data: **10,000 reviews**

---

# 7. Machine Learning Model

## Logistic Regression Classifier

A Logistic Regression model was selected as the first classification algorithm.

Although its name contains "Regression", it is commonly used for classification problems.

The model learns relationships between:

```

Text features (TF-IDF values)
↓
Sentiment label

```

The goal is to identify patterns associated with positive and negative reviews.

---

# 8. Model Evaluation

The model performance was evaluated using:

- Accuracy
- Precision
- Recall
- F1-score


## Results

```

```
          precision    recall    f1-score
```

Class 0          0.90       0.88       0.89

Class 1          0.89       0.91       0.90

Accuracy: 0.89

```

---

# 9. Interpretation of Results

## Accuracy

The model achieved an accuracy of:

```

89%

```

This means that approximately:

```

8,900 out of 10,000 test reviews

```

were correctly classified.

---

## Precision

Precision measures how often predictions are correct.

Results:

- Negative reviews: **90%**
- Positive reviews: **89%**

The model produces reliable predictions for both categories.

---

## Recall

Recall measures the ability to identify all real examples of a category.

Results:

- Negative reviews: **88%**
- Positive reviews: **91%**

The model is slightly better at detecting positive reviews.

---

## F1-score

The F1-score combines precision and recall.

Results:

- Negative reviews: **0.89**
- Positive reviews: **0.90**

The balanced scores indicate that the model does not favor one sentiment category over another.

---

# 10. Key Insights

## Insight 1 — Balanced Sentiment Dataset

The dataset contains an almost equal number of positive and negative reviews.

This provides a reliable foundation for sentiment classification without significant class imbalance issues.

---

## Insight 2 — Text Contains Strong Sentiment Signals

The model achieved 89% accuracy using only review text.

This demonstrates that vocabulary and word patterns contain meaningful information about user opinions.

---

## Insight 3 — Machine Learning Can Automate Review Analysis

The developed model can automatically classify new movie reviews without manual analysis.

Potential applications:

- Customer feedback monitoring
- Brand reputation analysis
- Automated review categorization
- Opinion mining

---

# 11. Limitations and Future Improvements

Although the model achieved good performance, some improvements could be explored:

## Advanced NLP Models

Compare the current approach with:

- Naive Bayes
- Support Vector Machines
- LSTM Neural Networks
- Transformer models (BERT)


## Error Analysis

Analyze incorrectly classified reviews to understand:

- Ambiguous sentences
- Sarcasm
- Context limitations


## Feature Improvements

Explore:

- Word embeddings
- N-grams
- Sentiment lexicons


---

# Conclusion

This project demonstrated a complete NLP workflow, from raw textual data exploration to predictive modeling.

The main steps were:

1. Understanding the dataset
2. Checking data quality
3. Exploring sentiment distribution
4. Cleaning and preprocessing text data
5. Transforming text into numerical features using TF-IDF
6. Training a classification model
7. Evaluating performance and extracting insights

The final model achieved **89% accuracy**, showing that machine learning techniques can effectively identify sentiment patterns in movie reviews.

This project highlights the importance of combining **data preparation, analytical reasoning, and machine learning** to transform unstructured text into actionable insights.
