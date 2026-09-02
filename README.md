# Disease Prediction Using Machine Learning

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Machine%20Learning-orange)
![Kaggle](https://img.shields.io/badge/Kaggle-Dataset-20BEFF?logo=kaggle)
![Status](https://img.shields.io/badge/Project-Academic-success)

## Assignment Information

| Information    | Details                                                                                              |
| -------------- | ---------------------------------------------------------------------------------------------------- |
| Title          | **Disease Prediction using Machine Learning**                                                        |
| Course Title   | **Special Study in Information and Communication Technology (Federated AI Security for Healthcare)** |
| Course Code    | **ICT 6700**                                                                                         |
| Course Teacher | **Dr. M A Moyeen - Assistant Professor, IICT, KUET**                                                 |

## Student Information

| Information | Details                                                  |
| ----------- | -------------------------------------------------------- |
| Name        | **Md. Arif Khan**                                        |
| Roll No     | **2671560**                                              |
| Semester    | **July-2026**                                            |
| Program     | **M.Sc. Eng. in ICT**                                    |
| University  | **Khulna University of Engineering & Technology (KUET)** |

---

## Project Overview

This project implements a **Disease Prediction System using Machine Learning**. The system predicts a possible disease from a patient's reported symptoms using supervised classification algorithms.

The project is developed as part of the academic requirements for the **M.Sc. Eng. in ICT** program at **Khulna University of Engineering & Technology (KUET)**.

**[Check Live Project on Kaggle](https://www.kaggle.com/code/arifkpi/disease-prediction-using-machine-learning)**

### Key Workflow

- Real-world healthcare dataset preprocessing
- Exploratory data analysis
- Feature preparation and encoding
- Stratified train-test splitting
- Multiple machine learning classification algorithms
- Model performance comparison
- Accuracy, Precision, Recall/Sensitivity, Specificity and F1-Score evaluation
- Confusion matrix analysis
- Random Forest feature importance analysis
- Interactive symptom-based disease prediction

> **Important:** This is an academic machine learning project. Predictions are for educational and research purposes only and must not be considered a medical diagnosis or a substitute for professional healthcare advice.

---

## Kaggle Dataset

This project uses the **Health Symptoms and Disease Prediction Dataset** available on Kaggle.

### Dataset Preview

**[View Dataset on Kaggle](https://www.kaggle.com/datasets/devikshah/health-symptoms-and-disease-prediction-dataset)**

The dataset contains symptom-related features and a `prognosis` target representing the disease class. The Kaggle data card describes binary symptom columns where `1` indicates that a symptom is present and `0` indicates that it is absent. It also contains additional healthcare-related fields, including medicine information.

The primary file used is:

```text
training.csv
```

The Kaggle dataset contains **136 columns**.

---

## Problem Statement

Given a set of symptoms reported by a patient, can a machine learning model classify the most likely disease category?

This project treats disease prediction as a **multiclass classification problem**:

- **Input:** Patient symptoms
- **Output:** Predicted disease (`prognosis`)

---

## Objectives

1. Preprocess a real-world healthcare dataset.
2. Identify and prepare suitable symptom features.
3. Handle duplicate and unsuitable data.
4. Encode disease labels for machine learning.
5. Train multiple classification algorithms.
6. Compare the performance of different models.
7. Evaluate models using several classification metrics.
8. Visualize model performance using graphs and confusion matrices.
9. Identify important symptoms using Random Forest feature importance.
10. Build a simple symptom-based prediction interface.

---

## Data Preprocessing

The preprocessing workflow includes:

- Loading the Kaggle dataset.
- Inspecting dataset structure and data types.
- Checking missing values.
- Detecting and removing duplicate records.
- Examining disease/class distribution.
- Removing extremely rare disease classes that do not contain enough samples for reliable stratified splitting.
- Separating the `prognosis` target from the input features.
- Selecting numeric symptom features for the machine learning models.
- Encoding disease labels using `LabelEncoder`.
- Splitting the dataset into training and testing sets using stratification.

### Handling Non-Numeric Data

The dataset contains non-numeric descriptive fields, including medicine/treatment information such as:

```text
Inhaled corticosteroids, bronchodilators
```

These text fields are not directly suitable as numerical inputs for the selected machine learning algorithms. Therefore, the modeling pipeline uses numeric symptom-related features and excludes unsuitable text fields.

---

## Machine Learning Models

### Logistic Regression

Used as a strong classification baseline. Despite its name, Logistic Regression is a **classification algorithm** and is appropriate for predicting disease categories.

### Support Vector Machine (SVM)

SVM attempts to find effective decision boundaries between disease classes. Feature scaling is applied before training.

### Gaussian Naive Bayes

A lightweight probabilistic classifier used as an additional baseline model.

### Random Forest

An ensemble of decision trees that can capture nonlinear relationships between symptoms and disease classes. It is also used for feature-importance analysis.

### XGBoost

A gradient-boosting classifier included as a powerful ensemble learning approach for comparison.

---

## Evaluation Metrics

| Metric                   | Purpose                                                      |
| ------------------------ | ------------------------------------------------------------ |
| **Accuracy**             | Overall percentage of correctly classified samples           |
| **Precision**            | Correctness of positive disease predictions                  |
| **Recall / Sensitivity** | Ability to identify samples belonging to each disease        |
| **Specificity**          | Ability to identify samples not belonging to a disease class |
| **F1-Score**             | Harmonic mean of precision and recall                        |

For this multiclass problem, macro-averaged Precision, Recall and F1-Score are used. Mean one-vs-rest specificity is calculated across disease classes.

---

## Results

The notebook automatically generates the model comparison in:

```text
results/model_comparison.csv
```

| Model                |              Accuracy |             Precision |  Recall / Sensitivity |           Specificity |              F1-Score |
| -------------------- | --------------------: | --------------------: | --------------------: | --------------------: | --------------------: |
| Logistic Regression  | Generated by notebook | Generated by notebook | Generated by notebook | Generated by notebook | Generated by notebook |
| SVM                  | Generated by notebook | Generated by notebook | Generated by notebook | Generated by notebook | Generated by notebook |
| Gaussian Naive Bayes | Generated by notebook | Generated by notebook | Generated by notebook | Generated by notebook | Generated by notebook |
| Random Forest        | Generated by notebook | Generated by notebook | Generated by notebook | Generated by notebook | Generated by notebook |
| XGBoost              | Generated by notebook | Generated by notebook | Generated by notebook | Generated by notebook | Generated by notebook |

The best-performing model is automatically selected according to the highest **macro F1-Score**.

> **Note:** Final numerical results should be copied from `results/model_comparison.csv` after the notebook has been executed successfully.

---

## Visualizations

Generated figures are stored in the `results/` directory.

### Disease Distribution

```text
results/target_distribution.png
```

Shows the distribution of disease classes after preprocessing.

### Model Comparison

```text
results/model_comparison.png
```

Compares Accuracy, Precision, Recall/Sensitivity, Specificity and F1-Score.

### Best Model Confusion Matrix

```text
results/confusion_matrix_best_model.png
```

Shows the classification performance of the selected best model.

Individual confusion matrices are also generated for each model.

### Random Forest Feature Importance

```text
results/random_forest_feature_importance.png
```

Shows the top 20 symptoms/features according to Random Forest importance.

---

## Project Structure

```text
disease-prediction-using-machine-learning/
│
├── disease-prediction-using-machine-learning.ipynb
├── README.md
└── dataset/
└── ├── training.csv
└── results/
    ├── target_distribution.png
    ├── model_comparison.csv
    ├── model_comparison.png
    ├── confusion_matrix_best_model.png
    ├── confusion_matrix_logistic_regression.png
    ├── confusion_matrix_svm.png
    ├── confusion_matrix_gaussian_naive_bayes.png
    ├── confusion_matrix_random_forest.png
    ├── confusion_matrix_xgboost.png
    ├── random_forest_feature_importance.png
    └── feature_importance.csv
```

---

## Technologies Used

- **Python**
- **Pandas** — data manipulation
- **NumPy** — numerical computation
- **Matplotlib** — visualization
- **Seaborn** — statistical visualization
- **Scikit-learn** — preprocessing, machine learning and evaluation
- **XGBoost** — gradient boosting classification
- **Kaggle** — dataset and notebook environment
- **Jupyter Notebook** — project implementation

---

## How to Run

### Kaggle

1. Open the [Health Symptoms and Disease Prediction Dataset](https://www.kaggle.com/datasets/devikshah/health-symptoms-and-disease-prediction-dataset).
2. Create or open a Kaggle Notebook.
3. Add the dataset as an input.
4. Upload or paste the project notebook.
5. Run the notebook from the first cell to the last.
6. Review the generated metrics, plots and prediction results.

### Local Jupyter Notebook

Install the required packages:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn xgboost jupyter
```

Then launch Jupyter:

```bash
jupyter notebook
```

Open the notebook and update the dataset path if necessary.

---

## Prediction System

The notebook includes an interactive symptom-based prediction function.

Example input:

```text
itching, skin rash, headache
```

The system:

1. Reads the symptoms entered by the user.
2. Matches them against available symptom features.
3. Creates a binary feature vector.
4. Sends the feature vector to the selected model.
5. Returns the predicted disease.
6. Displays top predictions when probability estimates are available.

---

## Limitations

- The dataset is intended for educational/research use and does not represent a clinical diagnostic system.
- Dataset quality and class distribution can affect model performance.
- Extremely rare disease classes were excluded to support reliable stratified train-test splitting.
- The models use numeric symptom indicators rather than full natural-language clinical descriptions.
- High accuracy on this dataset does not guarantee real-world clinical accuracy.
- The prediction system should not be used for medical diagnosis or treatment decisions.

---

## Conclusion

This project demonstrates how machine learning classification techniques can be applied to symptom-based disease prediction.

The workflow covers healthcare dataset preprocessing, feature selection, disease-label encoding, stratified train-test splitting, model training, evaluation, visualization and interactive prediction.

Five machine learning approaches—**Logistic Regression, SVM, Gaussian Naive Bayes, Random Forest and XGBoost**—are compared using Accuracy, Precision, Recall/Sensitivity, Specificity and F1-Score.

The project provides a practical academic example of applying machine learning to a healthcare-related classification problem while emphasizing proper preprocessing, model comparison and responsible interpretation of predictions.

---

## Academic Information

**Md. Arif Khan**  
**Roll No.: 2671560**  
**Semester: July-2026**  
**M.Sc. Eng. in ICT**  
**Khulna University of Engineering & Technology (KUET)**

---

## Dataset Attribution

**Health Symptoms and Disease Prediction Dataset**  
Kaggle: https://www.kaggle.com/datasets/devikshah/health-symptoms-and-disease-prediction-dataset

Please refer to the original Kaggle dataset page for the current dataset license and attribution requirements.

---

## Disclaimer

This project is developed strictly for **academic, educational and research purposes**. It is not a medical device and should not be used to diagnose diseases, recommend medication, or make healthcare decisions. Users should consult qualified healthcare professionals for medical advice, diagnosis and treatment.
