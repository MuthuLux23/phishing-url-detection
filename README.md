

#Phishing Website URL Detection using Random Forest Classifier

1. Problem Statement
  Phishing is a common cyber‑attack where fake websites imitate legitimate ones to steal sensitive information such as passwords, banking details, and personal data. These phishing URLs often look very similar to real URLs, making it difficult for normal users to identify them.

Goal of this project:

Build a machine learning model using a Random Forest Classifier that can automatically detect whether a given website URL is phishing or legitimate.


#2. Dataset
For this project we use a phishing dataset (phishing.csv) that contains:

Pre‑computed numeric features for each website (e.g. UsingIP, LongURL, ShortURL, HTTPS, …)
A target column class:
 1 → phishing website
-1 → legitimate website
Additionally, we define a small 20‑sample dataset of URLs for quick testing and demos.

#3. Features Used
From the full dataset, we use a small set of simple, interpretable features:

UsingIP
LongURL
ShortURL
HTTPS

#4. Methodology / Project Flow

┌─────────────────────────────────┐
│            Input URL            │
└────────────────┬────────────────┘
                 │
                 ▼
┌─────────────────────────────────┐
│       Feature Extraction        │
│  • UsingIP         • ShortURL   │
│  • LongURL         • HTTPS      │
└────────────────┬────────────────┘
                 │
                 ▼
┌─────────────────────────────────┐
│     Random Forest Classifier    │
│          (rf_model.pkl)         │
└────────────────┬────────────────┘
                 │
                 ▼
┌─────────────────────────────────┐
│          Prediction             │
│    Legitimate / Phishing      │
└─────────────────────────────────┘
                   │
            
#5. Technologies Used

Language: Python
Libraries:
pandas               – data handling
scikit-learn         – Random Forest, train/test split, accuracy
re                   – regular expressions (detect IP addresses in URLs)
streamlit (optional) – for simple web UI

#6. How It Works 

Step 1: Collect and load a labeled phishing dataset into Python using pandas.

Step 2: Select important URL‑based features and split the data into training and testing sets.

Step 3: Train a Random Forest classifier on the training data.

Step 4: Evaluate the model on the test data using accuracy (and other metrics if needed).

Step 5: For any new URL, extract the same features, give them to the trained model, and show whether the URL is phishing or legitimate.
 
#7.Future Scope:

--Add more URL features to improve accuracy.
--Use the full phishing dataset instead of only a few columns.
--Try other ML algorithms and compare with Random Forest.
--Create a simple web or mobile interface for users.
--Retrain the model regularly with new phishing URLs.

