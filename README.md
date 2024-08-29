# Toxic Comment Classification

This project focuses on classifying toxic comments using machine learning models. The primary objective is to develop, implement, and evaluate a text classifier that can effectively identify toxic comments in the provided dataset. The project involves data preprocessing, model selection, and evaluation using both generative and discriminative methods.

## Table of Contents
1. [Motivation](#motivation)
2. [Objectives](#objectives)
3. [Dataset](#dataset)
4. [Data Preprocessing](#data-preprocessing)
5. [Model Selection](#model-selection)
6. [Training and Evaluation](#training-and-evaluation)
7. [Results](#results)
8. [Conclusion](#conclusion)
9. [Future Recommendations](#future-recommendations)
10. [Installation](#installation)
11. [Usage](#usage)

## Motivation

Identifying toxic speech is crucial for enhancing user experience and complying with legal requirements. Platforms with high levels of toxic content may experience decreased interaction and could face regulatory issues. Therefore, developing a robust system to detect and manage toxic comments is essential.

## Objectives

- To design and implement a text classification system capable of detecting toxic comments.
- To justify the selection of preprocessing techniques and modeling choices.
- To compare the performance of generative and discriminative models and evaluate their effectiveness.

## Dataset

The dataset consists of comments labeled as either toxic or non-toxic. The data required significant preprocessing to remove noise and ensure consistency. The preprocessing steps are detailed below.

## Data Preprocessing

The preprocessing steps performed on the dataset include:

1. **Substring Removal**: Specific substrings such as "SDATA_5" and "EDATA_5" were removed.
2. **Special Character Removal**: Non-alphanumeric characters and extra whitespaces were eliminated.
3. **URL Removal**: Hyperlinks starting with "http" were discarded.
4. **Text Normalization**: All text was converted to lowercase to maintain uniformity.
5. **Tokenization**: The text was split into individual words (tokens).
6. **Stopword Removal**: Common English stopwords were excluded to reduce noise.
7. **Lemmatization**: Words were reduced to their base forms for consistency and analysis.

These preprocessing steps help clean the data and prepare it for efficient and accurate model training.

## Model Selection

Two types of models were chosen for this task:

1. **Generative Model: Multinomial Naive Bayes (MNB)**
   - A probability-based classifier suitable for text classification.
   - Handles multiple classes effectively by assuming feature independence within each class.
   - Hyperparameter tuning was conducted using alpha values of [0.01, 0.1, 1.0].

2. **Discriminative Model: Random Forest**
   - An ensemble learning method that uses decision trees.
   - Creates diverse trees and aggregates predictions for robust classification.
   - Hyperparameter tuning involved adjusting `n_estimators` values of [100, 200].

## Training and Evaluation

- The training process involved loading and preprocessing the dataset, vectorizing the text data, and handling class imbalance using the Adaptive Synthetic (ADASYN) resampling technique.
- GridSearchCV was utilized for hyperparameter tuning and cross-validation.
- Model performance was measured using the F1 score.

## Results

- **Multinomial Naive Bayes**: This generative model outperformed the Random Forest classifier in this specific dataset. The optimal performance was observed with a 0.3 subset size during training.
- **Random Forest**: Performed moderately well, with the best results at a 0.7 subset size.

## Conclusion

The Multinomial Naive Bayes model demonstrated superior performance in identifying toxic comments when compared to the Random Forest model. This suggests that generative models may be more effective for this particular text classification task.

## Future Recommendations

- Investigate additional preprocessing techniques to further improve model accuracy.
- Experiment with other generative and discriminative models, such as Support Vector Machines (SVM) and Deep Learning models.
- Explore the use of domain-specific embeddings or pre-trained language models for enhanced feature representation.

## Installation

To install the necessary packages, run:

```bash
pip install -r requirements.txt
