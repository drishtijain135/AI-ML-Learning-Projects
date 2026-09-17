# Resume Classification

A Natural Language Processing and Machine Learning project that classifies resumes into different job-related categories.

## Overview

This project uses resume text data to train a machine learning classification model.

The notebook performs text preprocessing, feature extraction, model training, and resume category prediction.

## Features

- Load resume data from a CSV file
- Explore the resume dataset
- Check resume categories
- Visualize category distribution
- Handle class imbalance using oversampling
- Clean resume text
- Convert text into numerical features using TF-IDF
- Encode resume categories using Label Encoding
- Train a Support Vector Machine classification model
- Predict the category of a new resume

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Machine Learning Concepts

- Natural Language Processing
- Text preprocessing
- TF-IDF Vectorization
- Label Encoding
- Cosine similarity-based text representation
- Support Vector Machine
- One-vs-Rest Classification
- Train-test split
- Accuracy evaluation
- Oversampling for class imbalance

## Project Workflow

1. Load the resume dataset.
2. Explore the dataset and resume categories.
3. Visualize the distribution of resume categories.
4. Balance the dataset using oversampling.
5. Clean the resume text by removing unwanted characters and symbols.
6. Convert category names into numerical labels.
7. Convert resume text into TF-IDF features.
8. Split the data into training and testing sets.
9. Train a Support Vector Machine classifier.
10. Evaluate the model using accuracy.
11. Predict the category of a new resume.

## Project Files

- `Resume Classification.ipynb` - Main Jupyter Notebook
- `Resume.csv` - Dataset used by the notebook
- `requirements.txt` - Required Python libraries
- `README.md` - Project documentation

## How to Run

### 1. Install the required libraries

```bash
pip install -r requirements.txt
