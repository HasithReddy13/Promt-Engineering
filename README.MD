{\rtf1\ansi\ansicpg1252\cocoartf2867
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\froman\fcharset0 Times-Bold;\f1\froman\fcharset0 Times-Roman;\f2\fmodern\fcharset0 Courier;
}
{\colortbl;\red255\green255\blue255;\red0\green0\blue0;}
{\*\expandedcolortbl;;\cssrgb\c0\c0\c0;}
{\*\listtable{\list\listtemplateid1\listhybrid{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat0\levelspace360\levelindent0{\*\levelmarker \{disc\}}{\leveltext\leveltemplateid1\'01\uc0\u8226 ;}{\levelnumbers;}\fi-360\li720\lin720 }{\listname ;}\listid1}
{\list\listtemplateid2\listhybrid{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat0\levelspace360\levelindent0{\*\levelmarker \{disc\}}{\leveltext\leveltemplateid101\'01\uc0\u8226 ;}{\levelnumbers;}\fi-360\li720\lin720 }{\listname ;}\listid2}
{\list\listtemplateid3\listhybrid{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat0\levelspace360\levelindent0{\*\levelmarker \{disc\}}{\leveltext\leveltemplateid201\'01\uc0\u8226 ;}{\levelnumbers;}\fi-360\li720\lin720 }{\listname ;}\listid3}
{\list\listtemplateid4\listhybrid{\listlevel\levelnfc0\levelnfcn0\leveljc0\leveljcn0\levelfollow0\levelstartat1\levelspace360\levelindent0{\*\levelmarker \{decimal\}}{\leveltext\leveltemplateid301\'01\'00;}{\levelnumbers\'01;}\fi-360\li720\lin720 }{\listname ;}\listid4}
{\list\listtemplateid5\listhybrid{\listlevel\levelnfc0\levelnfcn0\leveljc0\leveljcn0\levelfollow0\levelstartat1\levelspace360\levelindent0{\*\levelmarker \{decimal\}}{\leveltext\leveltemplateid401\'01\'00;}{\levelnumbers\'01;}\fi-360\li720\lin720 }{\listname ;}\listid5}
{\list\listtemplateid6\listhybrid{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat0\levelspace360\levelindent0{\*\levelmarker \{disc\}}{\leveltext\leveltemplateid501\'01\uc0\u8226 ;}{\levelnumbers;}\fi-360\li720\lin720 }{\listname ;}\listid6}
{\list\listtemplateid7\listhybrid{\listlevel\levelnfc0\levelnfcn0\leveljc0\leveljcn0\levelfollow0\levelstartat1\levelspace360\levelindent0{\*\levelmarker \{decimal\}}{\leveltext\leveltemplateid601\'01\'00;}{\levelnumbers\'01;}\fi-360\li720\lin720 }{\listname ;}\listid7}}
{\*\listoverridetable{\listoverride\listid1\listoverridecount0\ls1}{\listoverride\listid2\listoverridecount0\ls2}{\listoverride\listid3\listoverridecount0\ls3}{\listoverride\listid4\listoverridecount0\ls4}{\listoverride\listid5\listoverridecount0\ls5}{\listoverride\listid6\listoverridecount0\ls6}{\listoverride\listid7\listoverridecount0\ls7}}
\margl1440\margr1440\vieww11520\viewh8400\viewkind0
\deftab720
\pard\pardeftab720\sa321\partightenfactor0

\f0\b\fs48 \cf0 \expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Financial Sentiment Analysis: Domain-Specific Fine-Tuning of DistilBERT\
\pard\pardeftab720\sa298\partightenfactor0

\fs36 \cf0 \uc0\u55357 \u56524  Project Overview\
\pard\pardeftab720\sa240\partightenfactor0

\f1\b0\fs24 \cf0 This repository contains a professional-grade implementation of domain-specific fine-tuning using 
\f0\b DistilBERT
\f1\b0  for financial sentiment classification. General-purpose Large Language Models (LLMs) often struggle with the nuanced, context-dependent "directional" linguistics of finance\'97where terms like "narrowing losses" or "diluted earnings" carry polarity distinct from standard prose.\
This project bridges that gap by implementing a custom classification head and a weighted loss strategy to achieve high-precision sentiment scoring on the 
\f0\b Financial Phrasebank
\f1\b0  dataset.\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 Key Performance Metrics\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls1\ilvl0
\fs24 \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Peak Validation Accuracy:
\f1\b0  97.62%\
\ls1\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Final Test Accuracy:
\f1\b0  94.5%\
\ls1\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Model Backbone:
\f1\b0  
\f2\fs26 distilbert-base-uncased
\f1\fs24 \
\ls1\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Domain:
\f1\b0  Financial News & Market Sentiment\
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \uc0\u55357 \u56960  Key Technical Features\
\pard\pardeftab720\sa280\partightenfactor0

\fs28 \cf0 1. Custom Architecture with Layer Normalization\
\pard\pardeftab720\sa240\partightenfactor0

\f1\b0\fs24 \cf0 Standard sequence classification heads can be unstable during the initial stages of domain adaptation. This implementation bypasses the default 
\f2\fs26 AutoModelForSequenceClassification
\f1\fs24  head in favor of a specialized custom architecture:\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls2\ilvl0
\f0\b \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Feature Extraction:
\f1\b0  Utilizes the hidden state of the 
\f2\fs26 [CLS]
\f1\fs24  token from the DistilBERT backbone.\
\ls2\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Non-Linear Projection:
\f1\b0  A linear layer ($768 \\rightarrow 768$) with ReLU activation to process contextual embeddings.\
\ls2\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Explicit Layer Normalization:
\f1\b0  Implementation of 
\f2\fs26 nn.LayerNorm
\f1\fs24  to standardize feature embeddings. This stabilizes the second-order moments of the gradients, ensuring smoother convergence and mitigating internal covariate shift during fine-tuning.\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 2. Weighted Loss Strategy (Imbalance Mitigation)\
\pard\pardeftab720\sa240\partightenfactor0

\f1\b0\fs24 \cf0 Financial datasets are frequently skewed toward "Neutral" reporting, which can bias models toward the majority class. We implemented a 
\f2\fs26 WeightedTrainer
\f1\fs24  utilizing a custom loss function:\
\pard\pardeftab720\partightenfactor0
\cf0 $$L_\{weighted\} = -\\sum w_i y_i \\log(\\hat\{y\}_i)$$\
\pard\pardeftab720\sa240\partightenfactor0
\cf0 Where $w_i$ is calculated to be inversely proportional to class frequency. This forces the model to penalize errors on minority "Positive" and "Negative" classes more heavily, ensuring higher recall for market-moving sentiments.\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 3. Rigorous Hyperparameter Optimization\
\pard\pardeftab720\sa240\partightenfactor0

\f1\b0\fs24 \cf0 We conducted a systematic grid search across three distinct configurations to optimize performance while monitoring for overfitting:\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls3\ilvl0
\f0\b \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Optimal Configuration:
\f1\b0  Learning Rate of $5 \\times 10^\{-5\}$ over 3 epochs provided the best balance between convergence speed and generalization.\
\ls3\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Weight Capture:
\f1\b0  Utilized 
\f2\fs26 load_best_model_at_end=True
\f1\fs24  to ensure the final weights were captured at the global minimum of the validation loss.\
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \uc0\u55357 \u56522  Dataset & Preprocessing\
\pard\pardeftab720\sa280\partightenfactor0

\fs28 \cf0 Data Source\
\pard\pardeftab720\sa240\partightenfactor0

\f1\b0\fs24 \cf0 The 
\f0\b Financial Phrasebank
\f1\b0  (
\f2\fs26 FinanceMTEB/financial_phrasebank
\f1\fs24 ) dataset (All-Agree subset) was used, consisting of sentences where 100% of annotators agreed on the sentiment label.\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 Cleaning & Tokenization\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls4\ilvl0
\fs24 \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	1	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Entity Masking:
\f1\b0  Regex-based removal of stock tickers (e.g., 
\f2\fs26 $AAPL
\f1\fs24 ) to prevent brand-specific bias.\
\ls4\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	2	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Noise Reduction:
\f1\b0  Removal of URLs and non-alphanumeric noise to focus the attention mechanism on linguistic cues.\
\ls4\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	3	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Partitioning:
\f1\b0  A strict 
\f0\b 80/10/10 split
\f1\b0  (Training, Validation, Test) was used to ensure rigorous evaluation.\
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \uc0\u55357 \u56520  Experimental Results\
\pard\pardeftab720\sa240\partightenfactor0

\f1\b0\fs24 \cf0 | 
\f0\b Experiment
\f1\b0  | 
\f0\b Learning Rate
\f1\b0  | 
\f0\b Epochs
\f1\b0  | 
\f0\b Val Accuracy
\f1\b0  | 
\f0\b Result
\f1\b0  | | Exp 1 | 2e-5 | 3 | 95.24% | Stable, but slower | | 
\f0\b Exp 2
\f1\b0  | 
\f0\b 5e-5
\f1\b0  | 
\f0\b 3
\f1\b0  | 
\f0\b 97.62%
\f1\b0  | 
\f0\b Best Performance
\f1\b0  | | Exp 3 | 3e-5 | 5 | 97.62% | Reached plateau early |\
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \uc0\u55357 \u56589  Detailed Error Analysis\
\pard\pardeftab720\sa240\partightenfactor0

\f1\b0\fs24 \cf0 A qualitative review of the 7 failure cases (out of 127 test samples) identified two primary linguistic patterns:\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls5\ilvl0
\f0\b \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	1	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Lexical Inversion:
\f1\b0  The model misclassified phrases like "narrowed loss" as Negative. While "loss" is a negative token, "narrowed" inverts the financial polarity to Positive.\
\ls5\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	2	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Ambiguous Neutrality:
\f1\b0  Routine market data (e.g., "Stock closed at 10.71") was occasionally flagged as Negative, indicating an over-sensitivity to price volatility tokens in the training data.\
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \uc0\u55357 \u57056 \u65039  Setup & Installation\
\pard\pardeftab720\sa280\partightenfactor0

\fs28 \cf0 Prerequisites\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls6\ilvl0
\f1\b0\fs24 \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Google Colab (Recommended for T4 GPU access) or local machine with CUDA.\
\ls6\ilvl0\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Python 3.8+\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 Installation\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls7\ilvl0
\fs24 \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	1	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Clone the repository:
\f1\b0 \uc0\u8232 
\f2\fs26 git clone [https://github.com/your-username/financial-sentiment-analysis.git](https://github.com/your-username/financial-sentiment-analysis.git)\
\pard\tx220\tx720\pardeftab720\li720\fi-720\partightenfactor0
\ls7\ilvl0\cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	2	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 cd financial-sentiment-analysis\
\ls7\ilvl0\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	3	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 \
\pard\tx220\tx720\pardeftab720\li720\fi-720\partightenfactor0
\ls7\ilvl0
\f1\fs24 \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	4	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 \
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls7\ilvl0
\f0\b \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	5	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Install Dependencies:
\f1\b0 \uc0\u8232 
\f2\fs26 pip install transformers datasets evaluate accelerate scikit-learn seaborn matplotlib\
\pard\tx220\tx720\pardeftab720\li720\fi-720\partightenfactor0
\ls7\ilvl0\cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	6	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 \
\pard\tx220\tx720\pardeftab720\li720\fi-720\partightenfactor0
\ls7\ilvl0
\f1\fs24 \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	7	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 \
\pard\pardeftab720\sa298\partightenfactor0

\f0\b\fs36 \cf0 \uc0\u55357 \u56507  Usage (Inference)\
\pard\pardeftab720\partightenfactor0

\f2\b0\fs26 \cf0 from transformers import AutoTokenizer\
\
# Load fine-tuned model and tokenizer\
tokenizer = AutoTokenizer.from_pretrained("distilbert-base-uncased")\
\
def predict_sentiment(text):\
    inputs = tokenizer(text, return_tensors="pt", truncation=True, padding=True).to("cuda")\
    with torch.no_grad():\
        logits = model(**inputs).logits\
    return id2label[logits.argmax().item()]\
\
# Example test\
print(predict_sentiment("Profits surged as the company expanded its global footprint."))\
# Output: positive\
\
\pard\pardeftab720\sa240\partightenfactor0

\f1\fs24 \cf0 \
}