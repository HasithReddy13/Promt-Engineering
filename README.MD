Financial Sentiment Analysis: Domain-Specific Fine-Tuning of DistilBERT
📌 Project Overview
This repository contains a professional-grade implementation of domain-specific fine-tuning using DistilBERT for financial sentiment classification. General-purpose Large Language Models (LLMs) often struggle with the nuanced, context-dependent "directional" linguistics of finance—where terms like "narrowing losses" or "diluted earnings" carry polarity distinct from standard prose.
This project bridges that gap by implementing a custom classification head and a weighted loss strategy to achieve high-precision sentiment scoring on the Financial Phrasebank dataset.
Key Performance Metrics
	•	Peak Validation Accuracy: 97.62%
	•	Final Test Accuracy: 94.5%
	•	Model Backbone: distilbert-base-uncased
	•	Domain: Financial News & Market Sentiment
🚀 Key Technical Features
1. Custom Architecture with Layer Normalization
Standard sequence classification heads can be unstable during the initial stages of domain adaptation. This implementation bypasses the default AutoModelForSequenceClassification head in favor of a specialized custom architecture:
	•	Feature Extraction: Utilizes the hidden state of the [CLS] token from the DistilBERT backbone.
	•	Non-Linear Projection: A linear layer ($768 \rightarrow 768$) with ReLU activation to process contextual embeddings.
	•	Explicit Layer Normalization: Implementation of nn.LayerNorm to standardize feature embeddings. This stabilizes the second-order moments of the gradients, ensuring smoother convergence and mitigating internal covariate shift during fine-tuning.
2. Weighted Loss Strategy (Imbalance Mitigation)
Financial datasets are frequently skewed toward "Neutral" reporting, which can bias models toward the majority class. We implemented a WeightedTrainer utilizing a custom loss function:
$$L_{weighted} = -\sum w_i y_i \log(\hat{y}_i)$$
Where $w_i$ is calculated to be inversely proportional to class frequency. This forces the model to penalize errors on minority "Positive" and "Negative" classes more heavily, ensuring higher recall for market-moving sentiments.
3. Rigorous Hyperparameter Optimization
We conducted a systematic grid search across three distinct configurations to optimize performance while monitoring for overfitting:
	•	Optimal Configuration: Learning Rate of $5 \times 10^{-5}$ over 3 epochs provided the best balance between convergence speed and generalization.
	•	Weight Capture: Utilized load_best_model_at_end=True to ensure the final weights were captured at the global minimum of the validation loss.
📊 Dataset & Preprocessing
Data Source
The Financial Phrasebank (FinanceMTEB/financial_phrasebank) dataset (All-Agree subset) was used, consisting of sentences where 100% of annotators agreed on the sentiment label.
Cleaning & Tokenization
	1	Entity Masking: Regex-based removal of stock tickers (e.g., $AAPL) to prevent brand-specific bias.
	2	Noise Reduction: Removal of URLs and non-alphanumeric noise to focus the attention mechanism on linguistic cues.
	3	Partitioning: A strict 80/10/10 split (Training, Validation, Test) was used to ensure rigorous evaluation.
📈 Experimental Results
| Experiment | Learning Rate | Epochs | Val Accuracy | Result | | Exp 1 | 2e-5 | 3 | 95.24% | Stable, but slower | | Exp 2 | 5e-5 | 3 | 97.62% | Best Performance | | Exp 3 | 3e-5 | 5 | 97.62% | Reached plateau early |
🔍 Detailed Error Analysis
A qualitative review of the 7 failure cases (out of 127 test samples) identified two primary linguistic patterns:
	1	Lexical Inversion: The model misclassified phrases like "narrowed loss" as Negative. While "loss" is a negative token, "narrowed" inverts the financial polarity to Positive.
	2	Ambiguous Neutrality: Routine market data (e.g., "Stock closed at 10.71") was occasionally flagged as Negative, indicating an over-sensitivity to price volatility tokens in the training data.
🛠️ Setup & Installation
Prerequisites
	•	Google Colab (Recommended for T4 GPU access) or local machine with CUDA.
	•	Python 3.8+
Installation
	1	Clone the repository: git clone [https://github.com/your-username/financial-sentiment-analysis.git](https://github.com/your-username/financial-sentiment-analysis.git)
	2	cd financial-sentiment-analysis
	3	
	4	
	5	Install Dependencies: pip install transformers datasets evaluate accelerate scikit-learn seaborn matplotlib
	6	
	7	
💻 Usage (Inference)
from transformers import AutoTokenizer

# Load fine-tuned model and tokenizer
tokenizer = AutoTokenizer.from_pretrained("distilbert-base-uncased")

def predict_sentiment(text):
    inputs = tokenizer(text, return_tensors="pt", truncation=True, padding=True).to("cuda")
    with torch.no_grad():
        logits = model(**inputs).logits
    return id2label[logits.argmax().item()]

# Example test
print(predict_sentiment("Profits surged as the company expanded its global footprint."))
# Output: positive



