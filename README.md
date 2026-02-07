# password_strength_classifier
This project implements a supervised machine learning classifier for evaluating password strength based on character-level patterns and structural properties of passwords.

## Problem Statement

Weak passwords remain a major security risk, often leading to account compromise and data breaches. Traditional password validation systems are typically rule-based, which makes them predictable and easy to bypass.

This project explores whether **machine learning models can more flexibly classify password strength** by learning patterns such as:
- character composition
- length and structure
- common substrings and repetitions

## Approach

This is framed as a **multi-class classification problem**:

- **Input**: raw password strings  
- **Output**: password strength labels (e.g. weak, medium, strong)

The pipeline consists of:

1. **Text Vectorization**
   - Passwords are transformed using **TF-IDF at the character level**
   - This captures local character patterns (n-grams) common in weak or strong passwords

2. **Model Training**
   Multiple models were trained and compared:
   - Decision Tree: A non-parametric supervised learning method for classification and regression.
   - Random Forest: An ensemble learning method for classification.
   - XGBoost: An optimized distributed gradient boosting library.
   - CatBoost: A gradient boosting on decision trees library.
   - Multi-layer Perceptron (MLP): A feedforward artificial neural network model.

3. **Evaluation**
   - Accuracy and precision were used as evaluation metrics
   - Emphasis was placed on precision to reduce false positives (classifying weak passwords as strong)

4. **Model Persistence**
   - The trained model and vectorizer were saved using `joblib`.

## Technologies Used

- **Python**
- **scikit-learn**
- **XGBoost**
- **CatBoost**
- **pandas / NumPy**
- **TF-IDF Vectorization**
