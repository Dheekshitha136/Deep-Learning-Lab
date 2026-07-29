# 🧠 Experiment 02: Implementation of a Multi-Layer Perceptron (MLP) for Multi-Class Image Classification

## 📖 Overview

This experiment demonstrates the implementation of a **Multi-Layer Perceptron (MLP)** using TensorFlow/Keras for multi-class image classification on the **Fashion-MNIST** dataset. The experiment also includes automated hyperparameter optimization using **RandomizedSearchCV** and demonstrates how an MLP successfully solves the **XOR problem**, which cannot be solved by a Single Layer Perceptron.

---

## 🎯 Objective

- Implement a Multi-Layer Perceptron (MLP) using TensorFlow/Keras.
- Perform image preprocessing and normalization.
- Train and evaluate an MLP on the Fashion-MNIST dataset.
- Optimize model performance using RandomizedSearchCV.
- Understand how hidden layers enable the MLP to solve the XOR problem.

---

## 📚 Background

A Multi-Layer Perceptron (MLP) is a feed-forward neural network consisting of an input layer, one or more hidden layers, and an output layer. Unlike the Single Layer Perceptron, an MLP uses non-linear activation functions, enabling it to learn complex, non-linearly separable patterns.

For image classification, the output layer uses the **Softmax activation function**, while hidden layers commonly use **ReLU**, **Tanh**, or **Sigmoid** activations.

---

## 📂 Dataset

**Dataset:** Fashion-MNIST

### Dataset Summary

| Attribute | Value |
|----------|------:|
| Training Images | 60,000 |
| Testing Images | 10,000 |
| Classes | 10 |
| Image Size | 28 × 28 |

The Fashion-MNIST dataset contains grayscale images of clothing items belonging to ten different categories and is commonly used for benchmarking image classification models.

---

## 🛠 Software & Libraries

- Python
- Jupyter Notebook
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Scikit-learn
- SciKeras

---

## ⚙️ Experimental Procedure

1. Load the Fashion-MNIST dataset.
2. Display sample images and class distribution.
3. Flatten and normalize image data.
4. Construct a Multi-Layer Perceptron.
5. Train the baseline model.
6. Evaluate the model using classification metrics.
7. Perform hyperparameter optimization using RandomizedSearchCV.
8. Retrain the model using the best hyperparameters.
9. Compare baseline and optimized models.
10. Implement and evaluate an MLP for XOR classification.

---

## 📊 Model Evaluation

The model performance was evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- Classification Report

---

## 🔧 Hyperparameter Optimization

RandomizedSearchCV with 5-fold cross-validation was used to optimize the following parameters:

- Number of Hidden Layers
- Hidden Neurons
- Learning Rate
- Batch Size
- Epochs
- Optimizer
- Activation Function
- Dropout Rate

The optimized model achieved better generalization and slightly improved classification performance compared to the baseline model.

---

## 🧪 Key Concepts Covered

- Multi-Layer Perceptron (MLP)
- Hidden Layers
- Dense Layers
- ReLU Activation
- Softmax Activation
- Categorical Cross Entropy
- Adam Optimizer
- Hyperparameter Optimization
- RandomizedSearchCV
- Fashion-MNIST Classification
- XOR Classification
- Non-Linear Decision Boundary

---

## 📁 Files Included

| File | Description |
|------|-------------|
| `Multi_Layer_Perceptron.ipynb` | Jupyter Notebook containing the implementation |
| `Deep_Learning_Lab_02_Report.pdf` | Detailed lab report |
| `README.md` | Experiment documentation |

---

## ✅ Results

The baseline MLP successfully classified Fashion-MNIST images with good accuracy. After hyperparameter optimization using RandomizedSearchCV, the optimized model achieved improved accuracy, precision, recall, and F1-score. The experiment also demonstrated that an MLP can successfully solve the XOR problem by learning a non-linear decision boundary, unlike a Single Layer Perceptron.

---

## 📌 Conclusion

This experiment demonstrated the implementation of a Multi-Layer Perceptron for multi-class image classification using the Fashion-MNIST dataset. Hyperparameter optimization improved the model's overall performance and generalization. The XOR experiment further illustrated the importance of hidden layers and non-linear activation functions, highlighting the advantages of MLPs over Single Layer Perceptrons for solving complex classification problems.

---

## 📖 References

1. Fashion-MNIST Dataset
2. Ian Goodfellow, Yoshua Bengio, Aaron Courville – *Deep Learning*
3. C. M. Bishop – *Pattern Recognition and Machine Learning*
4. TensorFlow/Keras Documentation
5. Scikit-learn Documentation

---

