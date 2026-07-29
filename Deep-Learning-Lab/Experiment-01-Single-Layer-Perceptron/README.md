# 🧠 Experiment 01: Implementation of a Single Layer Perceptron for Binary Classification

## 📖 Overview

This experiment focuses on implementing a **Single Layer Perceptron (SLP)** from scratch for binary classification using the **Banknote Authentication Dataset**. The objective is to understand the working of an artificial neuron, the perceptron learning algorithm, activation functions, and decision boundary formation. The experiment also demonstrates the perceptron learning process on basic Boolean logic gates (OR, AND, NOT, and XOR).

---

## 🎯 Objective

- Understand the concept of an artificial neuron.
- Implement the Single Layer Perceptron learning algorithm from scratch.
- Perform binary classification using a real-world dataset.
- Learn the importance of activation functions.
- Visualize the learning process through decision boundaries.
- Implement the perceptron for OR, AND, NOT, and XOR logic gates.

---

## 📚 Background

A Single Layer Perceptron is one of the earliest supervised learning algorithms used for binary classification. It computes a weighted sum of the input features, adds a bias term, and applies the **Step Activation Function** to generate the output.

Since it learns only a **linear decision boundary**, it can solve only **linearly separable** problems.

---

## 📂 Dataset

**Dataset:** Banknote Authentication Dataset

**Source:** UCI Machine Learning Repository

### Dataset Summary

| Attribute | Value |
|----------|------:|
| Total Samples | 1372 |
| Input Features | 4 |
| Target Classes | 2 |
| Missing Values | 0 |

### Input Features

- Variance
- Skewness
- Curtosis
- Entropy

### Target Classes

- **0** → Authentic Banknote
- **1** → Forged Banknote

---

## 🛠 Software & Libraries

- Python
- Jupyter Notebook
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

---

## ⚙️ Experimental Procedure

1. Load and explore the Banknote Authentication dataset.
2. Perform Exploratory Data Analysis (EDA).
3. Generate histograms, scatter plots, correlation heatmap, and boxplots.
4. Normalize the features using **Z-score normalization**.
5. Split the dataset into training and testing sets (80:20).
6. Implement the Single Layer Perceptron from scratch.
7. Train the model using the perceptron learning rule.
8. Evaluate the model using classification metrics.
9. Implement the perceptron for OR, AND, NOT, and XOR logic gates.
10. Observe the evolution of the decision boundary after weight updates.

---

## 📊 Model Evaluation

The trained perceptron was evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

---

## 🧪 Key Concepts Covered

- Artificial Neuron
- Single Layer Perceptron
- Step Activation Function
- Perceptron Learning Rule
- Weight & Bias Updates
- Decision Boundary
- Binary Classification
- Feature Normalization
- Logic Gate Classification
- Limitation of Perceptron (XOR Problem)

---

## 📁 Files Included

| File | Description |
|------|-------------|
| `Single_Layer_Perceptron.ipynb` | Jupyter Notebook containing the implementation |
| `Deep_Learning_Lab_01_Report.pdf` | Detailed lab report |
| `README.md` | Experiment documentation |

---

## ✅ Results

The Single Layer Perceptron successfully classified authentic and forged banknotes with high accuracy after feature normalization and training. The experiment also demonstrated successful learning of the OR, AND, and NOT logic gates. However, the perceptron failed to converge for the XOR gate, highlighting its limitation in solving non-linearly separable problems.

---

## 📌 Conclusion

This experiment provided a practical understanding of the Single Layer Perceptron and its learning algorithm. The model achieved strong classification performance on the Banknote Authentication dataset while illustrating how weight updates gradually form a decision boundary. The inability of the perceptron to solve the XOR problem also emphasized the need for Multi-Layer Perceptrons and deeper neural networks for non-linear classification tasks.

---

## 📖 References

1. UCI Machine Learning Repository – Banknote Authentication Dataset
2. F. Rosenblatt, *The Perceptron*, 1958
3. Ian Goodfellow, Yoshua Bengio, Aaron Courville – *Deep Learning*
4. TensorFlow & Scikit-learn Documentation

---

**Course:** CS3807 – Deep Learning Laboratory  
**Experiment:** 01 – Single Layer Perceptron for Binary Classification