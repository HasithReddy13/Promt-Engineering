Financial Sentiment Analysis: Domain-Specific Fine-Tuning of DistilBERT

📌 Project Overview

Sentiment analysis in the financial sector is notoriously difficult because general-purpose language models often fail to capture domain-specific "directional" linguistics. For example, the word "loss" is generally negative, but the phrase "narrowed loss" is a positive signal for investors.

This project addresses these challenges by fine-tuning a DistilBERT model on the Financial Phrasebank dataset. Beyond standard fine-tuning, this implementation features a custom classification architecture and a weighted loss strategy to ensure high-precision sentiment scoring, even with imbalanced data.

Final Results:

Validation Accuracy: 97.62%

Test Accuracy: 94.5%

Performance: Significant improvement over the base pre-trained model (which typically scores ~34% accuracy on this specialized task).

🚀 Key Technical Features

1. Custom Model Architecture

We moved beyond the standard library defaults by implementing a custom classification head. This head includes:

Projection Layer: A linear layer that processes the Transformer's contextual embeddings.

ReLU Activation: Adds non-linearity to capture complex sentiment patterns.

Explicit Layer Normalization: Standardizes data during training to prevent "gradient issues" and ensure stable convergence.

2. Weighted Loss Strategy

Financial news is often skewed toward "Neutral" reporting. To prevent the model from ignoring rare but critical "Positive" or "Negative" signals, we implemented a Weighted Cross-Entropy Loss. This forces the model to penalize errors on minority classes more heavily.

3. Professional Data Cleaning

The pipeline includes a custom regex-based cleaning function that removes:

Stock Tickers (e.g., $AAPL, $TSLA) to prevent brand bias.

Specialized URLs and non-alphanumeric noise.

🛠️ Setup & Installation Instructions

To reproduce these results or use the model for your own predictions, follow these clear steps.

1. Prerequisites

Python: Version 3.8 or higher.

Hardware: Access to an NVIDIA GPU is highly recommended. If you do not have one locally, use Google Colab (it provides a free T4 GPU).

2. Environment Configuration

If running locally, it is recommended to use a virtual environment:

# Create a virtual environment
python -m venv fin_env

# Activate it
# On Windows:
fin_env\Scripts\activate
# On Mac/Linux:
source fin_env/bin/activate


3. Installing Dependencies

Run the following command to install all necessary machine learning libraries:

pip install transformers datasets evaluate accelerate scikit-learn seaborn matplotlib torch


4. Running the Notebook (Step-by-Step)

Upload to Colab: Upload the Untitled2-4.ipynb file to your Google Drive and open it with Google Colab.

Enable GPU: Go to Edit -> Notebook settings -> Select T4 GPU from the Hardware accelerator dropdown -> Save.

Execution: Click Runtime -> Run all.

The script will automatically download the DistilBERT weights.

It will perform three hyperparameter experiments to find the best settings.

It will generate a Confusion Matrix and a Classification Report at the end.

🔍 Model Evaluation

Results Summary

Metric

Performance

Peak Validation Accuracy

97.62%

Final Test Accuracy

94.49%

Evaluation Set

10% Unseen Data

Error Analysis (Pattern Identification)

Out of 127 test samples, the model missed only 7.

Identified Pattern: The model primarily struggles with Lexical Inversion. For instance, it may misclassify "narrowed loss" because the token "loss" is strongly associated with negative sentiment, even when the context "narrowed" makes it positive.

💻 Usage Example

After the final cell in the notebook is run, you can use the predict_sentiment function for real-time analysis:

# Example Usage:
text = "The company's quarterly revenue exceeded analyst estimates by 15%."
result = predict_sentiment(text)
print(f"Predicted Sentiment: {result}") 
# Output: Predicted Sentiment: positive


📄 License

This project is licensed under the MIT License.
