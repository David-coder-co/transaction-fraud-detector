## Introduction
Financial fraud is a significant challenge for banks and businesses, leading to substantial monetary losses and reputational damage. This project builds a machine learning model for fraud detection, leveraging real-world transaction data to classify transactions as fraudulent or legitimate.

## Dataset Description
The dataset contains transaction records with various features such as:
- Demographic Information: Gender, Age, Account Type
- Transaction Details: Transaction Amount, Location, Time, and Date
- Account Information: Account Balance, Merchant ID
- Categorical Features: Encoded customer details, state information, and fraud labels

## Key Steps in the Project
###  Data Preprocessing
- Checked for missing values and handled them appropriately.
- Identified categorical and numerical features.
- Converted date-related features into datetime format and extracted useful features (e.g., hour, day, month, weekday)
- Dropped unnecessary columns such as Customer_ID, Transaction_ID, Merchant_ID, Customer_Contact, and Transaction_Location.

### Feature Engineering
- Encoded categorical variables:
  - Label encoding for binary categories.
  - One-hot encoding for low-cardinality categorical features.
  - Frequency encoding for high-cardinality categorical features.
  - Hash encoding for text-based features.
- Transformed cyclical features (Transaction time attributes) using Sine and Cosine transformation.
- Standardized numerical features using StandardScaler to normalize transaction amounts, age, and account balances.

### Handling Imbalanced Data
Fraudulent transactions were significantly fewer than legitimate ones. To address this:
- Undersampling: Randomly sampled the majority class (legitimate transactions) to match the number of fraud cases.
- Oversampling (SMOTE): Applied Synthetic Minority Over-sampling Technique (SMOTE) to generate synthetic fraud cases and balance the dataset.

 ### Model Training
- Algorithm: Logistic Regression (baseline model)
- Train-test split: 80-20% split of the balanced dataset
- Performance Metrics:
  - Confusion Matrix to visualize false positives and false negatives
  - Precision, Recall, F1-Score to measure model effectiveness
  - ROC-AUC Score to evaluate model discrimination capability

### Model Evaluation & Results
- Initial results from undersampling led to 50% accuracy, showing model bias.
- After applying SMOTE oversampling, the model improved in recall and precision.
- ROC-AUC score improved, indicating a better ability to differentiate fraud cases from legitimate ones.

## How to Run the Project
### Requirements
Install the necessary dependencies using: pip install -r requirements.txt
### Running the Model
1. Load the dataset and perform preprocessing
2. Train the model.
3. Evaluate the model.

## Future Improvements
- Test Additional Algorithms (e.g. XGBoost, Neural Networks)
- Feature Selection to improve model interpretability.
- Deploy the model using Flask or FastAPI.
- Experiment with anomaly detection techniques.

## Contribution & Contact
If you have any suggestions or improvements, feel free to contribute! You can connect with me on LinkedIn or check out my other projects.
