Credit Card Fraud Detection (Task 5)
This project develops a classification model to detect fraudulent credit card transactions, addressing class imbalance and minimizing false positives while ensuring high accuracy. It fulfills the requirements of Task 5 for an internship assignment, including feature engineering, model training, and evaluation.
Task Objectives

Develop a classification model to detect fraudulent credit card transactions efficiently.
Use a dataset with transaction details (e.g., amount, timestamps).
Address class imbalance using techniques like oversampling (SMOTE).
Engineer meaningful features such as transaction frequency and spending patterns.
Evaluate model performance with a focus on minimizing false positives.
Submit a GitHub repository with clear code, preprocessing steps, model selection, and evaluation details.

Project Structure

fraud_detection.py: Main script with data loading, preprocessing, model training, and evaluation.
requirements.txt: List of dependencies.
README.md: Project documentation.

Dataset
The dataset is sourced from Kaggle: Credit Card Fraud Detection. It contains:

Features: Time, V1-V28 (anonymized), Amount.
Target: Class (0 = non-fraud, 1 = fraud).
Rows: ~284,807 transactions.
Class distribution: Highly imbalanced (492 fraud cases).

Setup and Steps to Run
Running in Google Colab (Recommended)

Open Google Colab: colab.research.google.com.
Upload fraud_detection.py to your Colab environment.
Install dependencies:!pip install -r requirements.txt


Set up Kaggle API:
Download your kaggle.json from Kaggle (Account > API > Create New API Token).
Upload it to Colab:from google.colab import files
files.upload()  # Upload kaggle.json
!mkdir -p ~/.kaggle
!mv kaggle.json ~/.kaggle/
!chmod 600 ~/.kaggle/kaggle.json




Run the script:!python fraud_detection.py



Running Locally

Clone this repository:git clone https://github.com/<your-username>/credit-card-fraud-detection-task5.git
cd credit-card-fraud-detection-task5


Create a virtual environment and install dependencies:python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt


Set up Kaggle API:
Place kaggle.json in ~/.kaggle/ (or C:\Users\<YourUser>\.kaggle\ on Windows).
Ensure permissions: chmod 600 ~/.kaggle/kaggle.json.


Run the script:python fraud_detection.py



Methodology

Data Loading: Downloads the dataset using kagglehub.
Feature Engineering:
hour: Extracted from Time (hour of the day).
transaction_freq: Frequency of transactions per V1.
amount_zscore: Z-score of the Amount to detect outliers.


Class Imbalance: Uses SMOTE to oversample the minority class (fraud).
Models:
Neural Network: 3-layer model with Dropout for regularization.
Random Forest: 100 estimators for comparison.
