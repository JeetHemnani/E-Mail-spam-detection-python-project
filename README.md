Email Spam Detection

Introduction

This project is a learning prototype for building an Email Spam Detection system using Machine Learning. We use the Email Spam Classification Dataset (purusinghvi) from Kaggle and train a Logistic Regression model to classify emails as spam or ham (not spam).

Dataset

Source: Kaggle — Email Spam Classification Dataset (purusinghvi)


Size: 83,448 email messages

Columns:

label: 1 = spam, 0 = ham

text: raw email content

Libraries & Dependencies

All core steps are implemented in Python using the following libraries:

pandas: data loading and manipulation

numpy: numerical operations

scikit-learn: vectorization and model training

nltk: natural language processing utilities (stopwords)

matplotlib: EDA visualizations

joblib: saving the trained model

Install via:

pip install -r requirements.txt

Exploratory Data Analysis (EDA)

Missing & Duplicate Checks

No null values in label or text columns.

Zero duplicate messages.

Label Distribution

Spam: 43,910 (52.6%)

Ham: 39,538 (47.4%)

Text Length Statistics

Metric

Characters

Words

Mean

1,663

283

Std Dev

4,179

725

Min

1

1

25%

449

80

50%

879

152

75%

1,861

312

Max

598,705

101,984

Top Words & Samples

After basic cleaning (lowercase, punctuation removal, stopword filtering), the most frequent words included: free, call, now, get, txt, claim, reply, stop, mobile, prize.

Sample Spam:

"Congratulations! You have won a free ticket. Call now to claim your prize."

"WINNER! Text WIN to 12345 to receive your reward."

"Limited time offer: Get cheap meds delivered right to your door."

Sample Ham:

"Hey, are we still meeting for lunch tomorrow?"

"Don't forget to send the report by end of day."

"Can you pick up groceries on your way home?"

Model Building

Train/Test Split

80% training, 20% testing

Stratified by label to preserve spam/ham ratio

Vectorization

TF-IDF features via TfidfVectorizer with:

lowercase=True

stop_words='english'

token_pattern=r"\b\w+\b"

Classifier

Logistic Regression (C=1.0, max_iter=1000)

Training & Evaluation

Fit the vectorizer and model on the training set

Evaluate on the test set

Performance metrics:

Accuracy: ~98.0%

Precision, Recall, F1-score: high scores for both classes

Confusion Matrix: low false positives/negatives

Results

Final Test Accuracy: 98.0% (Logistic Regression)
