# MSAI-699-Capstone

# AI Capstone: YouTube Video Popularity Prediction

## Overview

This project demonstrates a machine learning model designed to predict the popularity of YouTube videos based on early metadata such as likes, dislikes, comments, and category. The model uses logistic regression and evaluates performance through 5-fold stratified cross-validation.

The code outputs fold-by-fold metrics, a classification report, a confusion matrix, and basic error analysis of misclassified videos. It is designed to support future integration with a deployment pipeline using FastAPI.


## File

**`model_testing_debugging.py`**  
Main script that:
- Loads and cleans the dataset
- Engineers engagement-based features
- Scales numeric inputs
- Runs 5-fold cross-validation
- Prints detailed performance metrics
- Performs basic error analysis


## Dataset

- Source: Publicly available YouTube video metadata
- File used: `USvideos3.csv`  
- Target variable: `popular`  
  - Videos in the top 25% of view count are labeled as 1 (popular)
  - All others are labeled as 0 (not popular)

## Features Used

- `likes`  
- `dislikes`  
- `comment_total`  
- `category_id`  
- `engagement_ratio`: (likes + comments) / (views + 1)  
- `like_dislike_ratio`: (likes + 1) / (dislikes + 1)


## Results

Cross-validation produces:
- **Mean Accuracy**: ~92.26%
- **Mean Precision**: ~90.55%
- **Mean Recall**: ~77.15%
- **Mean F1 Score**: ~83.28%

