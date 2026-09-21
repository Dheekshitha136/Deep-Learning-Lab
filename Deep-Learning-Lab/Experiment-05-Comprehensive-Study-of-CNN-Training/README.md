Deep Learning Lab 5 – CNN Training and Optimization
Overview

Implementation and experimental analysis of CNN training using MobileNetV2 on the Oxford-IIIT Pet Dataset. The experiment studies how initialization, regularization, optimization, hyperparameters, transfer learning, fine-tuning, and cross-validation affect classification performance.

Experiments
Weight Initialization: Zero, Random, Xavier/Glorot, He
Regularization: L2, Dropout, Batch Normalization
Optimizers: SGD, Momentum, RMSProp, Adam
Hyperparameter Tuning: Learning Rate, Batch Size, Dropout
Transfer Learning: Feature Extraction and Fine-Tuning
5-Fold Cross-Validation
Final Model Evaluation
Additional Configuration Analysis
Dataset

Oxford-IIIT Pet Dataset – 37 cat and dog breeds.

Split	Images
Training	2944
Validation	736
Test	3669

Images are resized to 224 × 224 × 3.

Final Configuration
Model: MobileNetV2
Learning Rate: 0.001
Dropout: 0.25
Batch Size: 64
Fine-Tuning: No
Final Results
Metric	Result
Mean CV Accuracy	91.03%
CV Standard Deviation	1.20%
Test Accuracy	89.07%
Precision	89.50%
Recall	89.01%
F1-Score	89.00%
Training Time	42.45 s
Parameters	2,426,725
Technologies Used

Python, TensorFlow/Keras, MobileNetV2, NumPy, Pandas, Matplotlib, Scikit-learn, Jupyter Notebook

Repository Contents
Jupyter notebooks containing the implementations and outputs
Generated plots and visualizations
Final laboratory report
Experimental results and analysis
