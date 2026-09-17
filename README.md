#  Phishing URL Detection Using Machine Learning

## demo link: "https://scoff-cusp-hesitancy.ngrok-free.dev" 

##  Project Name : Phishing URL Detection Using Machine Learning
##  College Name : EGS Pillay Engineering College
##  Team members : Muthulakshmi A , Shinas begum M
##  Problem Statement

Phishing websites use malicious URLs to trick users into visiting fake websites and revealing sensitive information such as passwords, banking details, and personal data.

The objective of this project is to develop a machine learning-based system that analyzes URL characteristics and classifies a given URL as **Legitimate** or **Phishing**.

##  System Architecture

```text
User Input (URL)
        ↓
Data Preprocessing
        ↓
Feature Extraction
        ↓
Feature Conversion
        ↓
Random Forest Classifier
        ↓
Classification
   ↙             ↘
Legitimate      Phishing
        ↓
Streamlit Deployment
```

##  Model Used

### Random Forest Classifier

Random Forest is an ensemble machine learning algorithm that combines multiple decision trees to perform classification.

In this project, the model learns patterns from URL-based features and predicts whether the input URL is **Legitimate** or **Phishing**.

##  Technologies Used

* **Python** – Programming
* **Pandas** – Data processing
* **NumPy** – Numerical operations
* **Scikit-learn** – Machine learning
* **Random Forest** – Classification
* **Streamlit** – Web application deployment
* **Pickle** – Saving and loading the trained model

##  Project Structure

```text
Phishing-URL-Detection/
│
├── app.py
├── rf_model.pkl
├── phishing dataset.csv
└── README.md
```

### Files Description

| File               | Description                     |
| ------------------ | ------------------------------- |
| `app.py`           | Streamlit application           |
| `rf_model.pkl`     | Trained Random Forest model     |
| `dataset.csv`      | Dataset used for model training |
| `requirements.txt` | Required Python libraries       |
| `README.md`        | Project documentation           |

##  How It Works

1. **User enters a URL** into the Streamlit application.
2. The system performs **URL preprocessing**.
3. Relevant features are **extracted from the URL**.
4. The extracted features are converted into a numerical format suitable for the machine learning model.
5. The trained **Random Forest Classifier** analyzes the features.
6. The system classifies the URL as:

   * **Legitimate**
   * **Phishing**
7. The prediction is displayed through the **Streamlit web interface**.

##  Future Scope

* Integrate real-time website and URL reputation checking.
* Add external threat intelligence APIs.
* Improve detection using larger and more diverse datasets.
* Explore advanced machine learning and deep learning models.
* Develop a browser extension for real-time phishing detection.
* Add continuous model training with newly identified phishing URLs.
