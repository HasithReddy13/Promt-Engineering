Financial Sentiment Analysis: Domain-Specific Fine-Tuning

📌 Project Overview

This project focuses on the specialized task of Financial Sentiment Analysis. Standard AI models often struggle with financial language; for example, they might think the word "loss" is always bad, but they miss that a "narrowed loss" is actually a positive sign for a company.

This project solves this by fine-tuning a DistilBERT model specifically for financial news. We added custom layers like Layer Normalization to make the training more stable and used a Weighted Loss strategy to ensure the model doesn't get biased toward "Neutral" statements.

🏆 Final Results

97.6% Validation Accuracy

94.5% Test Accuracy

Domain-Specific Logic: Successfully identifies complex financial signals.

🚀 Key Technical Features

Custom Architecture: We built a custom "head" for the model that standardizes data during training, preventing errors.

Weighted Training: This ensures that rare "Positive" or "Negative" news is treated with high importance compared to common "Neutral" news.

Smart Data Cleaning: Uses code to automatically strip out stock tickers (like $AAPL) and website links to focus only on the sentiment of the words.

🛠️ Step-by-Step Setup Instructions

1. Requirements

Python: You need Python 3.8 or higher installed.

GPU: This project uses a Graphics Card (GPU) for speed. If your computer doesn't have one, Google Colab is highly recommended because it provides a free T4 GPU.

2. Environment Setup

If you are running this locally, install the required libraries:

pip install transformers datasets evaluate accelerate scikit-learn seaborn matplotlib torch


3. Running in Google Colab (Recommended)

Upload: Upload the provided .ipynb file to your Google Colab.

Turn on GPU: - Click Edit -> Notebook settings.

Select T4 GPU from the "Hardware accelerator" list.

Click Save.

Execute: Click Runtime -> Run all.

🔍 How We Evaluate Success

We use professional metrics to verify the model:

Confusion Matrix: A visual grid showing exactly where the model succeeded or failed.

Classification Report: Detailed scores for Precision, Recall, and F1-score.

Error Analysis: We manually checked errors to understand model limits, specifically regarding complex accounting phrases.

💻 How to Predict Sentiment

Once you have run the notebook, you can use the built-in function to test any sentence:

text = "The company reported a massive growth in revenue this year."
print(predict_sentiment(text))
# Output: positive


