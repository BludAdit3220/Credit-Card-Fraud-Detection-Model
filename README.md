# 💳 Credit Card Fraud Detection

This project uses various supervised machine learning models to detect fraudulent credit card transactions. It includes preprocessing, model training, hyperparameter tuning with `GridSearchCV`, evaluation, comparison, and saving the best-performing model to disk.

---

## 📁 Project Structure
├── best_model.pkl # 🔒 Final best-performing model (Random Forest)
├── DataPreprocessing.ipynb # 🧹 Notebook to clean and preprocess raw data
├── MLtraining.ipynb # 🤖 Notebook to train and evaluate models
├── README.md # 📘 Project overview and usage guide
├── creditcard_splits/ # 📂 Original data split into 10 parts
│ ├── creditcard_part_1.csv
│ ├── ...
│ └── creditcard_part_10.csv
└── creditcard_cleaned_splits/ # 📂 Cleaned data used for training
├── creditcard_cleaned_part_1.csv
├── ...
└── creditcard_cleaned_part_9.csv


---

## 🚀 Workflow Summary

### 1. 🔄 Data Preprocessing
- Performed in `DataPreprocessing.ipynb`
- Combines and cleans all CSV files from `creditcard_splits/`
- Saves cleaned CSVs into `creditcard_cleaned_splits/`

### 2. 🤖 Model Training
- Done in `MLtraining.ipynb`
- Trains and tunes the following models:
  - Logistic Regression
  - Decision Tree
  - Random Forest
- Uses `GridSearchCV` for hyperparameter tuning
- Evaluates models using:
  - Accuracy
  - F1-Score
  - AUC Score
- Automatically selects and saves the best model as `best_model.pkl`

---

## 🧪 How to Run

1. **Preprocess Data**
   Open and run `DataPreprocessing.ipynb` to generate cleaned data.

2. **Train & Save Best Model**
   Open and run `MLtraining.ipynb`. It will:
   - Train all models
   - Print evaluation metrics
   - Save the best model automatically to `best_model.pkl`

3. **Use the Model in Deployment**
   Load the model using:
   ```python
   import pickle

   with open("best_model.pkl", "rb") as f:
       model = pickle.load(f)
