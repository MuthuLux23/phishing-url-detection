# phishing-url-detection

#Phishing Website URL Detection using Random Forest Classifier

1. Problem Statement
Phishing is a common cyber‑attack where fake websites imitate legitimate ones to steal sensitive information such as passwords, banking details, and personal data. These phishing URLs often look very similar to real URLs, making it difficult for normal users to identify them.

Goal of this project:

Build a machine learning model using a Random Forest Classifier that can automatically detect whether a given website URL is phishing or legitimate.

The model should:

Learn patterns from a labeled phishing dataset
Extract simple features from URLs (length, presence of IP, HTTPS, shorteners, etc.)
Predict the class of a new URL entered by the user
Be easy to test and understand for students
2. Dataset
For this project we use a phishing dataset (phishing.csv) that contains:

Pre‑computed numeric features for each website (e.g. UsingIP, LongURL, ShortURL, HTTPS, …)
A target column class:
1 → phishing website
-1 → legitimate website
Additionally, we define a small 20‑sample dataset of URLs for quick testing and demos.

3. Features Used
From the full dataset, we use a small set of simple, interpretable features:

UsingIP

1 → URL uses normal domain (e.g. www.google.com)
-1 → URL contains an IP address (e.g. http://192.168.0.1/login)
LongURL

1 → URL length < 54 characters
0 → 54–75 characters
-1 → > 75 characters (very long URLs can be suspicious)
ShortURL

-1 → URL contains a common shortener domain (e.g. bit.ly, tinyurl.com)
1 → normal URL
HTTPS

1 → URL starts with https
-1 → URL does not use HTTPS
These features are easy to compute from a raw URL string and match a subset of the features in the dataset.

4. Methodology / Project Flow
Data Loading

Read phishing.csv using pandas.
Drop non‑useful columns like Index if present.
Data Preparation

Select feature columns: UsingIP, LongURL, ShortURL, HTTPS.
Select target column: class (1 = phishing, -1 = legitimate).
Convert labels to integer type.
Train–Test Split

Split data into training and testing sets
(70% training, 30% testing) using train_test_split with stratify to keep class balance.
Model Training (Random Forest)

Use RandomForestClassifier from scikit‑learn with:
n_estimators = 200
random_state = 42
Fit the model on the training data.
Model Evaluation

Predict on the test set.
Calculate accuracy using accuracy_score.
Optionally view precision, recall, F1‑score and confusion matrix.
URL Feature Extraction

Implement url_features(url) function to compute:
UsingIP, LongURL, ShortURL, HTTPS
This function is used both for:
creating small custom datasets
converting new user input URLs to model input
Prediction for User Input

Take URL from the user via input() (console) or text box (Streamlit).
Convert URL to features using url_features.
Use the trained Random Forest to predict if it is phishing or legitimate.
Display:
Extracted features
Final prediction (PHISHING / LEGITIMATE)
(Optional) Streamlit Deployment

Wrap the model and url_features into a simple Streamlit app with:
Text input for URL
Button: “Detect”
Output: prediction result and feature values
5. Technologies Used
Language: Python
Libraries:
pandas – data handling
scikit-learn – Random Forest, train/test split, accuracy
re – regular expressions (detect IP addresses in URLs)
streamlit (optional) – for simple web UI
6. How It Works (High‑Level)
The model is trained on historical examples of phishing and legitimate websites.
Each URL is represented by simple numeric features (e.g., length, HTTPS, IP).
The Random Forest learns combinations of these feature patterns that are typical for phishing and for legitimate sites.
When a new URL is entered:
The same features are computed.
The trained model outputs a prediction:
1 → phishing
-1 → legitimate
This helps users quickly get an automatic risk assessment of a URL.
7. Possible Improvements / Future Work
Add more advanced URL features (number of special characters, number of subdomains, suspicious keywords).
Use the full feature set from the original phishing dataset (not only 4 columns).
Include HTML and JavaScript content features (forms, iframes, redirects).
Try other algorithms (e.g., XGBoost, SVM, Logistic Regression) and compare performance.
Deploy as a proper web service (e.g., Streamlit Cloud, Flask + Heroku).
