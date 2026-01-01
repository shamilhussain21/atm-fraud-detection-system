#  ATM Transaction Fraud Detection System

---

##  Problem Statement

An Australian bank has been experiencing financial losses and reputational risks due to fraudulent ATM transactions. These fraudulent cases are rare but critical, making traditional fraud detection approaches ineffective.

To address this, PredCatch Analytics engaged me to build a predictive model capable of accurately identifying and flagging fraudulent ATM transactions in real time, helping the bank reduce and potentially eliminate such incidents.

The client provided multiple datasets containing both transactional and proprietary risk-related features to enrich the model.

---

##  Objectives

- Merge and analyze multiple data sources to build a consolidated fraud detection dataset.
- Handle missing values and ensure data integrity.
- Build a predictive model to classify ATM transactions as fraudulent or legitimate.
- Evaluate the model using appropriate classification metrics.
- Generate actionable insights to assist fraud prevention efforts.

---

##  Dataset Overview

The dataset included masked variables representing each transaction and several unique features provided by the client:

- **Transaction Location Scores** (`geo_scores`): Geographical risk associated with transaction locations.
- **Proprietary Index** (`Lambda_wts`): Internal bank-specific risk assessment index.
- **Network Turn-Around Times** (`Qset_tats`): Transaction processing time within the bank's ATM network.
- **Vulnerability Qualification Score** (`instance_scores`): Calculated score reflecting potential transaction vulnerability.

The target variable for prediction:

- `Target = 1`: Fraudulent transaction
- `Target = 0`: Clean transaction

---

##  Tech Stack

- **Programming Language**: Python  
- **Data Manipulation**: Pandas, NumPy  
- **Visualization**: Matplotlib, Seaborn  
- **Machine Learning**: Scikit-learn  
- **Model Used**: Random Forest Classifier  
- **Model Evaluation**: Cross-validation, Classification Metrics, ROC-AUC Curve

---

## 🔄 Project Workflow

### 1️⃣ Data Loading & Merging

- Loaded multiple datasets:
  - `Geo_scores.csv`
  - `instance_scores.csv`
  - `Lambda_wts.csv`
  - `Qset_tats.csv`
  - `train.csv`
  - `test_share.csv`
  
- Merged datasets on common identifiers (`id`, `Group`) to create a comprehensive dataset.

### 2️⃣ Data Inspection & Missing Value Handling

- Identified missing values in `geo_score` and `qsets_normalized_tat`.
- Handled missing values prior to model training to ensure data completeness.

### 3️⃣ Data Preprocessing

- Encoded categorical features (e.g., `Group` column).
- Performed necessary feature scaling or transformations.

### 4️⃣ Train-Test Split

- Applied **stratified train-test split** to preserve the class imbalance ratio.
- Split 80% for training and 20% for testing.

### 5️⃣ Model Development

- Built a **Random Forest Classifier** as the primary model.
- Trained on the processed dataset using default parameters.

### 6️⃣ Model Evaluation

- Evaluated model performance using:
  - Accuracy
  - Precision
  - Recall
  - F1-score
  - ROC-AUC Score
- Generated full classification reports.
- Plotted ROC Curve to visualize true positive vs false positive rates.

### 7️⃣ Cross-Validation

- Conducted 5-fold cross-validation on the training data.
- Computed cross-validated accuracy, precision, recall, and F1-score.

### 8️⃣ Final Prediction

- Applied the trained model to the unseen test dataset (`test_share.csv`).
- Generated predicted target values indicating whether each transaction was fraudulent (`Target = 1`) or clean (`Target = 0`).
- Merged predictions with transaction IDs to create a final output file:
  - **`predictions/Final Predictions.csv`** — containing transaction IDs and their predicted fraud labels.
  - **`predictions/Final_Target_Value.csv`** — containing only the predicted labels for submission.

---

## 📈 Model Performance Highlights

- Achieved high overall accuracy across train and test data.
- Maintained strong precision and acceptable recall despite class imbalance.
- ROC-AUC score indicated robust classification capability.
- Cross-validation confirmed model generalization and stability.

---

## 📌 Key Insights

- Random Forest effectively leveraged both transactional and proprietary features to detect fraud.
- Unique client-provided features (geo_scores, instance_scores, lambda_wt, qsets_normalized_tat) added significant predictive power.
- Stratified splitting was crucial for handling imbalanced fraud cases fairly.

---
## 📂 Project Structure

- `Banking_Domain.ipynb` — Jupyter Notebook with complete fraud detection analysis
- `Presentation.pptx` — Project presentation slides
- `output.html` — HTML export of the notebook
- `data/`
  - `Geo_scores.csv`
  - `instance_scores.csv`
  - `Lambda_wts.csv`
  - `Qset_tats.csv`
  - `train.csv`
  - `test_share.csv`
  - `test_share.csv.xlsx`
- `predictions/`
  - `Final Predictions.csv` — IDs with predicted target labels
  - `Final_Target_Value.csv` — Only target predictions for submission

---

## 🧠 Key Learnings

- Successfully built a full end-to-end fraud detection system using real-world multi-source transactional data.
- Gained hands-on experience with imbalanced classification problems and feature integration.
- Strengthened model evaluation, cross-validation, and practical fraud analytics techniques.

---

## 📧 Contact

For questions or collaboration, connect with me on [LinkedIn](https://www.linkedin.com/in/shamil-hussain-k-221190312) or view my full portfolio on [GitHub](https://github.com/shamilhussain21).

