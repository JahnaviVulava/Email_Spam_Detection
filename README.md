# Email_Spam_Detection
Email Spam Detection using Machine Learning | NLP | TF-IDF | Logistic Regression | Python

# Email Spam Detection using Machine Learning

## Project Overview

Email spam has become one of the most common cybersecurity problems, resulting in unwanted advertisements, phishing attacks, and fraudulent messages. This project aims to automatically classify emails as **Spam** or **Ham (Not Spam)** using Natural Language Processing (NLP) techniques and a Machine Learning model.

The project performs comprehensive text preprocessing, converts text into numerical feature vectors using **TF-IDF (Term Frequency-Inverse Document Frequency)**, and trains a **Logistic Regression** classifier to accurately distinguish spam emails from legitimate ones.

---

## Objectives

- Clean and preprocess raw email text.
- Extract meaningful textual features.
- Convert text into numerical feature vectors.
- Train a Machine Learning classifier.
- Predict whether an email is Spam or Ham.
- Evaluate model performance using appropriate evaluation metrics.

---

# Dataset

This project uses the **Mail Data Dataset** available on Kaggle.

**Dataset Link:**  
[Mail Data Dataset](https://www.kaggle.com/datasets/suraj452/mail-data)

## Dataset Description

The dataset contains a collection of email messages labeled into two categories.

| Column | Description |
|---------|-------------|
| Category | Email label (`spam` or `ham`) |
| Message | Actual email text |

### Target Classes

- **Spam (0)** – Unwanted, promotional, or fraudulent emails.
- **Ham (1)** – Legitimate emails.

This dataset is widely used for binary text classification and Natural Language Processing (NLP) tasks.

---

# Technologies Used

- Python
- Pandas
- NumPy
- BeautifulSoup
- spaCy
- NLTK
- Unidecode
- Scikit-learn
- Matplotlib
- Seaborn

---

# Data Preprocessing Pipeline

Raw email text cannot be directly used for machine learning. Therefore, several preprocessing techniques are applied before training the model.

## 1. HTML Tag Removal

Many email messages contain HTML formatting. HTML tags are removed to retain only meaningful textual content.

**Example**

```html
<b>Congratulations!</b>
```

becomes

```
Congratulations!
```

**Library Used**

- BeautifulSoup

---

## 2. Remove Accented Characters

Accented characters are converted into their standard English equivalents.

**Example**

```
café
naïve
résumé
```

becomes

```
cafe
naive
resume
```

**Library Used**

- Unidecode

---

## 3. Tokenization

Each email is divided into individual words (tokens).

**Example**

```
You won a free prize
```

becomes

```
["You", "won", "a", "free", "prize"]
```

**Library Used**

- spaCy

---

## 4. Stopword Removal

Frequently occurring words that contribute little to the meaning of a sentence are removed.

**Example**

```
the
is
and
of
to
```

**Library Used**

- NLTK

---

## 5. Lemmatization

Words are converted into their base or dictionary forms.

**Example**

```
running → run
studies → study
better → good
```

**Library Used**

- spaCy

---

# Feature Extraction

Machine learning algorithms require numerical input. Therefore, the cleaned text is transformed into numerical feature vectors using **TF-IDF (Term Frequency-Inverse Document Frequency)**.

## Advantages of TF-IDF

- Assigns higher importance to informative words.
- Reduces the influence of commonly occurring words.
- Produces sparse numerical vectors suitable for text classification.
- Improves classification performance.

**Library Used**

```python
sklearn.feature_extraction.text.TfidfVectorizer
```

---

# Machine Learning Model

This project uses **Logistic Regression** for binary classification.

## Why Logistic Regression?

- Fast and computationally efficient.
- Performs well on text classification problems.
- Easy to interpret.
- Produces high accuracy with TF-IDF features.

**Implementation**

```python
model = LogisticRegression()
model.fit(X_train_features, Y_train)
```

---

# Model Workflow

```
Dataset
      │
      ▼
Load Data
      │
      ▼
Text Preprocessing
      │
      ▼
TF-IDF Vectorization
      │
      ▼
Train-Test Split
      │
      ▼
Logistic Regression
      │
      ▼
Prediction
      │
      ▼
Model Evaluation
```

---

# System Architecture

The Email Spam Detection system follows the workflow below:

1. **Dataset Collection**
   - Load the Mail Data dataset containing labeled spam and ham email messages.

2. **Data Loading**
   - Read the dataset using the Pandas library and inspect it for missing or invalid values.

3. **Data Preprocessing**
   - Clean the email text by:
     - Removing HTML tags
     - Removing accented characters
     - Tokenizing the text
     - Removing stopwords
     - Performing lemmatization

4. **Feature Extraction**
   - Convert the processed text into numerical vectors using the **TF-IDF** technique.

5. **Train-Test Split**
   - Divide the dataset into training and testing sets for model evaluation.

6. **Model Training**
   - Train a **Logistic Regression** classifier using the TF-IDF feature vectors.

7. **Prediction**
   - Classify email messages as **Spam** or **Ham** using the trained model.

8. **Model Evaluation**
   - Measure the model's performance using **Accuracy Score** and **Confusion Matrix**.

---

# Model Evaluation

The trained model is evaluated using the following metrics:

- Accuracy Score
- Confusion Matrix

These metrics indicate how effectively the model distinguishes spam emails from legitimate emails.

---

# Project Structure

```
Email-Spam-Detection/
│
├── email_spam_detection.ipynb
├── mail_data.csv
├── README.md
└── requirements.txt
```

---

# Future Improvements

- Implement additional machine learning algorithms such as Naïve Bayes, Support Vector Machine (SVM), and Random Forest.
- Explore deep learning models such as LSTM and BERT.
- Build a real-time email spam detection web application using Streamlit or Flask.
- Develop a browser extension for automatic email filtering.
- Improve preprocessing techniques to enhance model accuracy.

---

# References

- **Kaggle Mail Data Dataset**  
  https://www.kaggle.com/datasets/suraj452/mail-data

- **Scikit-learn Documentation**  
  https://scikit-learn.org/

- **spaCy Documentation**  
  https://spacy.io/

- **NLTK Documentation**  
  https://www.nltk.org/

---

# Author

**Jahnavi Vulava**

Machine Learning | Artificial Intelligence | Natural Language Processing
