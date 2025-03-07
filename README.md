# Language Classification using Machine Learning

## Overview
This project implements a simple machine learning-based approach to automatically classify the language of a given text. The method involves preprocessing steps such as alphabet (script) detection and feature extraction, followed by classification using logistic regression with optimized hyperparameters.

## Features
- **Multilingual classification** of texts from a diverse dataset.
- **Script detection** to refine classification by narrowing language candidates.
- **TF-IDF vectorization** for feature extraction, specialized per script.
- **MultiScript Model**: Independent classifiers for different script categories.
- **Hyperparameter optimization** using grid search and cross-validation.
- **Handling of rare languages** through a script threshold mechanism.

## Dataset
The dataset is a labeled collection of multilingual text samples. To ensure balanced training, underrepresented languages are filtered, and overrepresented ones are limited in size.

## Model Pipeline
1. **Script Detection**: Identifies the dominant script of each text using Unicode ranges.
2. **Rare Language Handling**: Classifies texts as "rare language" if no script exceeds a 40% threshold.
3. **Feature Extraction**: Applies TF-IDF vectorization, optimized per script category.
4. **Feature rescaling:** Applies a standard  scaler to the features.
5. **Classification**: Uses logistic regression models trained per script.
6. **Evaluation**: The model is tested using a stratified train-test split and cross-validation.

## Results
- Achieved an **accuracy of 0.83** using a five-fold cross-validation method.
- Compact model with a **size of 56.34 MB**, making it efficient for deployment.
- Common misclassification occurs in **closely related languages** (e.g., Italian vs. Spanish).

## Future Improvements
- Enhance the TF-IDF vectorizer to include word-based features.
- Explore deep learning models for improved performance and a better vector representation.
- Expand training data to improve classification of underrepresented scripts.

## How to Run
1. Install dependencies: `pip install -r requirements.txt`
2. Notebook with the preprocessing and training : `main.ipynb`
3. Classify new texts using the notebook.

## Author
Marius Nadalin

