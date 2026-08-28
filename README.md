# Network Intrusion Detection System
A machine learning based Network Intrusion Detection System trained 
on the NSL-KDD dataset the standard benchmark for network security 
research. The system classifies network traffic into five categories 
and compares two models to find the best approach.

## Attack Categories
- Normal — legitimate network traffic
- DoS — Denial of Service attacks
- Probe — network scanning and surveillance
- R2L — Remote to Local unauthorized access
- U2R — User to Root privilege escalation

## Models
Two models trained and compared:

Decision Tree — fast, interpretable, strong baseline with feature 
importance analysis to understand which network features matter most.

ANN — two hidden layers, ReLU activation, Adam optimizer with early stopping to prevent overfitting.

## What makes this non-trivial
Real world network traffic data is heavily imbalanced attack types 
like U2R and R2L have very few samples compared to Normal traffic. 
SMOTE (Synthetic Minority Oversampling Technique) was used to balance 
the training data so both models actually learn minority attack classes 
instead of just predicting Normal for everything.

## Tech Stack
- Python
- Scikit-learn — Decision Tree, MLP, StandardScaler, LabelEncoder
- Imbalanced-learn — SMOTE
- Pandas — data loading and preprocessing
- Matplotlib and Seaborn — visualization
- Joblib — model serialization

## Dataset
Uses the NSL-KDD dataset an improved version of the KDD Cup 99 
dataset widely used in network intrusion detection research.

Download from: https://www.kaggle.com/datasets/hassan06/nslkdd

Place KDDTrain+.txt and KDDTest+.txt in the project root directory 
before running.

## Output
- Confusion matrices for both models
- Classification reports with precision, recall and F1 scores
- Feature importance chart showing top 10 most significant features
- Trained models saved as .pkl files for deployment

## Results
Decision Tree Accuracy: 99.43%
ANN Accuracy: 98.99%

Decision Tree outperformed ANN on minority attack classes — 
R2L F1: 0.93 and U2R F1: 0.65while being significantly 
faster to train. Full evaluation details in report.pdf.

## Course
Artificial Intelligence, 4th Semester, FAST-NUCES
