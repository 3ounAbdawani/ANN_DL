# Artificial Neural Network for Customer Churn Prediction

This project implements an **Artificial Neural Network (ANN)** using **TensorFlow/Keras** to predict whether a bank customer will leave the bank (customer churn).  
The model is trained on the **Churn_Modelling dataset** and includes full data preprocessing, training, and evaluation.

---

## Project Overview

The notebook demonstrates the full machine learning workflow:

1. **Data Preprocessing**
2. **Building an Artificial Neural Network**
3. **Training the Model**
4. **Making Predictions and Evaluating Performance**

The goal is to classify whether a customer will **stay (0)** or **leave (1)** the bank.

---

## Technologies Used

- Python
- NumPy
- Pandas
- TensorFlow / Keras
- Scikit-learn

---

## Dataset

The project uses the **Churn_Modelling.csv** dataset which contains customer information such as:

- Credit Score
- Geography
- Gender
- Age
- Balance
- Number of Products
- Estimated Salary

The target variable is:

- `1` → Customer left the bank  
- `0` → Customer stayed

---

## Data Preprocessing

Several preprocessing steps are applied before training the model:

### 1. Encoding Categorical Data
- **Label Encoding** for the `Gender` column
- **One-Hot Encoding** for the `Geography` column

### 2. Splitting the Dataset
The dataset is divided into:

- **Training set (80%)**
- **Test set (20%)**

### 3. Feature Scaling
`StandardScaler` is used to normalize input features for better ANN performance.

---

## Artificial Neural Network Architecture

The ANN is built using **Keras Sequential API**.

**Architecture:**

- Input Layer
- Hidden Layer (6 neurons, ReLU)
- Hidden Layer (6 neurons, ReLU)
- Output Layer (1 neuron, Sigmoid)

Activation functions:

- **ReLU** → Hidden layers
- **Sigmoid** → Output layer (binary classification)

---

## Model Training

The model is compiled with:

- **Optimizer:** Adam
- **Loss Function:** Binary Crossentropy
- **Metric:** Accuracy

Training parameters:
- **Batch Size:** 32
- **Epochs:** 100

---

## Predictions

The model performs:

1. **Single Customer Prediction**
2. **Test Set Predictions**

Example prediction:

```python
ann.predict(sc.transform([[...]])) > 0.5
```

If the output is:
- True → Customer likely to leave
- False → Customer likely to stay

---
## Model Evaluation

Model performance is evaluated using:
- **Confusion Matrix**
- **Accuracy Score**
Example:
```python
from sklearn.metrics import confusion_matrix, accuracy_score
```
