# XGBoost Model for user order and user churn prediction

## XGBoost & Data

XGBoost Website: https://xgboost.readthedocs.io
To install the XGBoost model, we can use the PIP installation method, for example, in the Windows operating system, Win+R shortcut keys to bring up the run box, enter cmd, enter the code in the pop-up interface and run: `pip install xgboost`
The data used come from a travel company, and the XGBoost model was employed to predict user order and user churn.

## XGBoost for Deal Prediction 
### Workflow
- Define the problem
- Data Collection
- Data Cleaning
- Feature Engineering and Processing
- Model Training
- Evaluation and Tuning
- Model Application 

## XGBoost for User Churn Prediction 
### Workflow
- Data Cleaning
- Data Pre-processing
- Missing Value Processing
- Correlation Analysis
- Dimension Reduction(PCA)
- Data normalization
- Model Training and Evaluation
- Feature Engineering 
- RFM Modeling and User Profiling
- RFM Analysis
- According Strategy

A random sample of 80% of the dataset is used as the training dataset, and the remaining 20% is used as the test dataset for data mining calculation according to the XGBoost function format. For the trained model, the test data is imported into it to get the prediction data. The trained model is evaluated by comparing the predicted data with the actual data by calculating the model evaluation metrics (AUC).

