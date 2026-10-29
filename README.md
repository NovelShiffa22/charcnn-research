# Char-CNN for SMS Spam Detection with Adversarial Robustness

## Overview
This repository contains the dataset, source code, and pre-trained models for the research paper proposing a Character-Level Convolutional Neural Network (Char-CNN) for SMS Spam Detection. The proposed model is specifically designed to handle adversarial text obfuscation (such as extreme spacing, vowel removal, and character substitution) where traditional Word-Level models and classical Machine Learning algorithms typically fail due to Out-of-Vocabulary (OOV) issues.

## Repository Structure
This repository consists of 5 main files:

1. `01_Proposed_Model_Training.ipynb`
   The primary Jupyter Notebook containing the data preparation, data augmentation (obfuscation injection), and the complete training pipeline for the proposed Char-CNN architecture.

2. `02_Model_Comparison_Evaluation.ipynb`
   The evaluation notebook used to compare the proposed Char-CNN against 7 baseline models (Naive Bayes, Decision Tree, SVM, Random Forest, Logistic Regression, Word-CNN, and Word-LSTM). It includes performance metrics (Accuracy, F1-Score), visualizations, and the final "Checkmate Scenarios" demonstrating the model's robustness against False Positives and False Negatives.

3. `combined_dataset.xlsx`
   The raw dataset containing labeled SMS messages (SPAM and HAM) used in this study.

4. `tokenizer_char.pkl`
   The saved character-level tokenizer generated during the training phase, ensuring consistent character index mapping during evaluation.

5. `char_cnn_spam_model.keras`
   The pre-trained weights and architecture of the proposed Char-CNN model.

## Requirements
To run the notebooks, ensure you have the following Python libraries installed:
* tensorflow (Keras)
* scikit-learn
* pandas
* numpy
* matplotlib
* seaborn
* openpyxl (for reading Excel files)

## How to Use
You have two options to reproduce the results of this study:

Option A: Full Retraining
Open and run all cells in 01_Proposed_Model_Training.ipynb. This will process the raw dataset, perform data augmentation, train the Char-CNN model from scratch, and automatically overwrite the .keras and .pkl files with your new training results.

Option B: Direct Evaluation (Recommended)
If you wish to bypass the training phase and directly evaluate the model's performance, simply open and run 02_Model_Comparison_Evaluation.ipynb. This script will automatically load the provided char_cnn_spam_model.keras and tokenizer_char.pkl to test the model against the baseline algorithms and the adversarial scenarios.

## Note on Blind Review
*This repository has been anonymized to comply with Double-Blind Peer Review guidelines. Author identities and affiliations will be updated upon the acceptance of the manuscript.*
