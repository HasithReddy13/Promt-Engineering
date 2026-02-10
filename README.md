{\rtf1\ansi\ansicpg1252\cocoartf2867
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\froman\fcharset0 Times-Bold;\f1\fnil\fcharset0 AppleColorEmoji;\f2\froman\fcharset0 Times-Roman;
\f3\fmodern\fcharset0 Courier;\f4\froman\fcharset0 TimesNewRomanPSMT;}
{\colortbl;\red255\green255\blue255;\red0\green0\blue0;}
{\*\expandedcolortbl;;\cssrgb\c0\c0\c0;}
{\*\listtable{\list\listtemplateid1\listhybrid{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat0\levelspace360\levelindent0{\*\levelmarker \{disc\}}{\leveltext\leveltemplateid1\'01\uc0\u8226 ;}{\levelnumbers;}\fi-360\li720\lin720 }{\listname ;}\listid1}
{\list\listtemplateid2\listhybrid{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat0\levelspace360\levelindent0{\*\levelmarker \{disc\}}{\leveltext\leveltemplateid101\'01\uc0\u8226 ;}{\levelnumbers;}\fi-360\li720\lin720 }{\listname ;}\listid2}
{\list\listtemplateid3\listhybrid{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat0\levelspace360\levelindent0{\*\levelmarker \{disc\}}{\leveltext\leveltemplateid201\'01\uc0\u8226 ;}{\levelnumbers;}\fi-360\li720\lin720 }{\listname ;}\listid3}
{\list\listtemplateid4\listhybrid{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat0\levelspace360\levelindent0{\*\levelmarker \{disc\}}{\leveltext\leveltemplateid301\'01\uc0\u8226 ;}{\levelnumbers;}\fi-360\li720\lin720 }{\listname ;}\listid4}
{\list\listtemplateid5\listhybrid{\listlevel\levelnfc0\levelnfcn0\leveljc0\leveljcn0\levelfollow0\levelstartat1\levelspace360\levelindent0{\*\levelmarker \{decimal\}}{\leveltext\leveltemplateid401\'01\'00;}{\levelnumbers\'01;}\fi-360\li720\lin720 }{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat0\levelspace360\levelindent0{\*\levelmarker \{circle\}}{\leveltext\leveltemplateid402\'01\uc0\u9702 ;}{\levelnumbers;}\fi-360\li1440\lin1440 }{\listname ;}\listid5}
{\list\listtemplateid6\listhybrid{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat0\levelspace360\levelindent0{\*\levelmarker \{disc\}}{\leveltext\leveltemplateid501\'01\uc0\u8226 ;}{\levelnumbers;}\fi-360\li720\lin720 }{\listname ;}\listid6}}
{\*\listoverridetable{\listoverride\listid1\listoverridecount0\ls1}{\listoverride\listid2\listoverridecount0\ls2}{\listoverride\listid3\listoverridecount0\ls3}{\listoverride\listid4\listoverridecount0\ls4}{\listoverride\listid5\listoverridecount0\ls5}{\listoverride\listid6\listoverridecount0\ls6}}
\margl1440\margr1440\vieww11520\viewh8400\viewkind0
\deftab720
\pard\pardeftab720\sa321\partightenfactor0

\f0\b\fs48 \cf0 \expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Financial Sentiment Analysis: Domain-Specific Fine-Tuning of DistilBERT\
\pard\pardeftab720\sa298\partightenfactor0

\f1\b0\fs36 \cf0 \uc0\u55357 \u56524 
\f0\b  Project Overview\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 Sentiment analysis in the financial sector is notoriously difficult because general-purpose language models often fail to capture domain-specific "directional" linguistics. For example, the word 
\f0\b "loss"
\f2\b0  is generally negative, but the phrase 
\f0\b "narrowed loss"
\f2\b0  is a positive signal for investors.\
This project addresses these challenges by fine-tuning a 
\f0\b DistilBERT
\f2\b0  model on the 
\f0\b Financial Phrasebank
\f2\b0  dataset. Beyond standard fine-tuning, this implementation features a custom classification architecture and a weighted loss strategy to ensure high-precision sentiment scoring, even with imbalanced data.\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 Final Results:\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls1\ilvl0
\fs24 \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Validation Accuracy:
\f2\b0  97.62%\
\ls1\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Test Accuracy:
\f2\b0  94.5%\
\ls1\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Performance:
\f2\b0  Significant improvement over the base pre-trained model (which typically scores ~34% accuracy on this specialized task).\
\pard\pardeftab720\sa298\partightenfactor0

\f1\fs36 \cf0 \uc0\u55357 \u56960 
\f0\b  Key Technical Features\
\pard\pardeftab720\sa280\partightenfactor0

\fs28 \cf0 1. Custom Model Architecture\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 We moved beyond the standard library defaults by implementing a custom classification head. This head includes:\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls2\ilvl0
\f0\b \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Projection Layer:
\f2\b0  A linear layer that processes the Transformer's contextual embeddings.\
\ls2\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 ReLU Activation:
\f2\b0  Adds non-linearity to capture complex sentiment patterns.\
\ls2\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Explicit Layer Normalization:
\f2\b0  Standardizes data during training to prevent "gradient issues" and ensure stable convergence.\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 2. Weighted Loss Strategy\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 Financial news is often skewed toward "Neutral" reporting. To prevent the model from ignoring rare but critical "Positive" or "Negative" signals, we implemented a 
\f0\b Weighted Cross-Entropy Loss
\f2\b0 . This forces the model to penalize errors on minority classes more heavily.\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 3. Professional Data Cleaning\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 The pipeline includes a custom regex-based cleaning function that removes:\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls3\ilvl0\cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Stock Tickers (e.g., $AAPL, $TSLA) to prevent brand bias.\
\ls3\ilvl0\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Specialized URLs and non-alphanumeric noise.\
\pard\pardeftab720\sa298\partightenfactor0

\f1\fs36 \cf0 \uc0\u55357 \u57056 \u65039 
\f0\b  Setup & Installation Instructions\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 To reproduce these results or use the model for your own predictions, follow these clear steps.\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 1. Prerequisites\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls4\ilvl0
\fs24 \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Python:
\f2\b0  Version 3.8 or higher.\
\ls4\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Hardware:
\f2\b0  Access to an NVIDIA GPU is highly recommended. If you do not have one locally, use 
\f0\b Google Colab
\f2\b0 (it provides a free T4 GPU).\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 2. Environment Configuration\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 If running locally, it is recommended to use a virtual environment:\
\pard\pardeftab720\partightenfactor0

\f3\fs26 \cf0 # Create a virtual environment\
python -m venv fin_env\
\
# Activate it\
# On Windows:\
fin_env\\Scripts\\activate\
# On Mac/Linux:\
source fin_env/bin/activate\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 3. Installing Dependencies\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 Run the following command to install all necessary machine learning libraries:\
\pard\pardeftab720\partightenfactor0

\f3\fs26 \cf0 pip install transformers datasets evaluate accelerate scikit-learn seaborn matplotlib torch\
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 4. Running the Notebook (Step-by-Step)\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls5\ilvl0
\fs24 \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	1	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Upload to Colab:
\f2\b0  Upload the 
\f3\fs26 Untitled2-4.ipynb
\f2\fs24  file to your Google Drive and open it with Google Colab.\
\ls5\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	2	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Enable GPU:
\f2\b0  Go to 
\f3\fs26 Edit
\f2\fs24  -> 
\f3\fs26 Notebook settings
\f2\fs24  -> Select 
\f3\fs26 T4 GPU
\f2\fs24  from the Hardware accelerator dropdown -> Save.\
\ls5\ilvl0
\f0\b \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	3	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Execution:
\f2\b0  Click 
\f3\fs26 Runtime
\f2\fs24  -> 
\f3\fs26 Run all
\f2\fs24 .\
\pard\tx940\tx1440\pardeftab720\li1440\fi-1440\sa240\partightenfactor0
\ls5\ilvl1\cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	
\f4 \uc0\u9702 
\f2 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 The script will automatically download the DistilBERT weights.\
\ls5\ilvl1\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	
\f4 \uc0\u9702 
\f2 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 It will perform three hyperparameter experiments to find the best settings.\
\ls5\ilvl1\kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	
\f4 \uc0\u9702 
\f2 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 It will generate a 
\f0\b Confusion Matrix
\f2\b0  and a 
\f0\b Classification Report
\f2\b0  at the end.\
\pard\pardeftab720\sa298\partightenfactor0

\f1\fs36 \cf0 \uc0\u55357 \u56589 
\f0\b  Model Evaluation\
\pard\pardeftab720\sa280\partightenfactor0

\fs28 \cf0 Results Summary\

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrt\brdrnil \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth2492\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx4320
\clvertalc \clshdrawnil \clwWidth1732\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\sa240\qc\partightenfactor0

\fs24 \cf0 Metric\cell 
\pard\intbl\itap1\pardeftab720\sa240\qc\partightenfactor0
\cf0 Performance\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth2492\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx4320
\clvertalc \clshdrawnil \clwWidth1732\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\sa240\partightenfactor0

\f2\b0 \cf0 Peak Validation Accuracy\cell 
\pard\intbl\itap1\pardeftab720\sa240\partightenfactor0
\cf0 97.62%\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth2492\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx4320
\clvertalc \clshdrawnil \clwWidth1732\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\sa240\partightenfactor0
\cf0 Final Test Accuracy\cell 
\pard\intbl\itap1\pardeftab720\sa240\partightenfactor0
\cf0 94.49%\cell \row

\itap1\trowd \taflags0 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrt\brdrnil \trbrdrr\brdrnil 
\clvertalc \clshdrawnil \clwWidth2492\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx4320
\clvertalc \clshdrawnil \clwWidth1732\clftsWidth3 \clmart10 \clmarl10 \clmarb10 \clmarr10 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadt20 \clpadl20 \clpadb20 \clpadr20 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\sa240\partightenfactor0
\cf0 Evaluation Set\cell 
\pard\intbl\itap1\pardeftab720\sa240\partightenfactor0
\cf0 10% Unseen Data\cell \lastrow\row
\pard\pardeftab720\sa280\partightenfactor0

\f0\b\fs28 \cf0 Error Analysis (Pattern Identification)\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 Out of 127 test samples, the model missed only 7.\
\pard\tx220\tx720\pardeftab720\li720\fi-720\sa240\partightenfactor0
\ls6\ilvl0
\f0\b \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {\listtext	\uc0\u8226 	}\expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 Identified Pattern:
\f2\b0  The model primarily struggles with 
\f0\b Lexical Inversion
\f2\b0 . For instance, it may misclassify "narrowed loss" because the token "loss" is strongly associated with negative sentiment, even when the context "narrowed" makes it positive.\
\pard\pardeftab720\sa298\partightenfactor0

\f1\fs36 \cf0 \uc0\u55357 \u56507 
\f0\b  Usage Example\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 After the final cell in the notebook is run, you can use the 
\f3\fs26 predict_sentiment
\f2\fs24  function for real-time analysis:\
\pard\pardeftab720\partightenfactor0

\f3\fs26 \cf0 # Example Usage:\
text = "The company's quarterly revenue exceeded analyst estimates by 15%."\
result = predict_sentiment(text)\
print(f"Predicted Sentiment: \{result\}") \
# Output: Predicted Sentiment: positive\
\pard\pardeftab720\sa298\partightenfactor0

\f1\fs36 \cf0 \uc0\u55357 \u56516 
\f0\b  License\
\pard\pardeftab720\sa240\partightenfactor0

\f2\b0\fs24 \cf0 This project is licensed under the MIT License.\
}