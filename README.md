# Assignment 2: Sentiment Classification

## Overview
This repository contains my Stage 1 submission for the CYSE 499 Assignment 2. The objective is to classify movie reviews as positive (1) or negative (0). I utilized a pre-trained `distilbert-base-uncased` model fine-tuned using PyTorch and Hugging Face Transformers.

## How to Run
1. Install the required packages via terminal:
   `pip install -r requirements.txt`
2. Open `stage1_notebook.ipynb` in an environment that supports Jupyter Notebooks (like VS Code or GitHub Codespaces).
3. Run all cells from top to bottom.
4. The notebook will automatically output its evaluation metrics and save the checkpoint to the `model_checkpoint/` directory, while generating the `public_test_predictions.csv` file.

## Loading the Checkpoint (For Stage 2 Inference)
To load the model later for inference without retraining, you can use:
```python
from transformers import AutoModelForSequenceClassification, AutoTokenizer
tokenizer = AutoTokenizer.from_pretrained("./model_checkpoint")
model = AutoModelForSequenceClassification.from_pretrained("./model_checkpoint")