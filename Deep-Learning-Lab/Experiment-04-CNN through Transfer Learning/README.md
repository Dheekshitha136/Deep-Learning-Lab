# Experiment 4 – Comparative Study of Deep CNN Architectures Using Transfer Learning

## About the Experiment

This experiment focuses on understanding and comparing different Convolutional Neural Network (CNN) architectures for image classification using the CIFAR-10 dataset.

The models implemented in this experiment are:

- LeNet-5
- AlexNet
- VGG16
- GoogleNet
- ResNet50

Along with comparing the architectures, transfer learning and fine tuning were also studied using VGG16 pretrained on ImageNet.

---

## Objectives

- To study the evolution of different CNN architectures.
- To implement and compare LeNet-5, AlexNet, VGG16, GoogleNet and ResNet50.
- To understand the concept of transfer learning.
- To study fine tuning of pretrained CNN models.
- To compare the models using different classification metrics.
- To study the effect of hyperparameters and optimizers on model performance.

---

## Dataset

The experiment was performed using the **CIFAR-10 dataset**.

| Property | Details |
|----------|---------|
| Training Images | 50,000 |
| Testing Images | 10,000 |
| Number of Classes | 10 |
| Image Size | 32 × 32 × 3 |

### Classes

- Airplane
- Automobile
- Bird
- Cat
- Deer
- Dog
- Frog
- Horse
- Ship
- Truck

The images were normalized before training.

---

## CNN Architectures

### 1. LeNet-5

LeNet-5 is a relatively small CNN consisting of convolution, pooling and fully connected layers. It was used as the simpler baseline architecture for comparison.

### 2. AlexNet

AlexNet is a deeper CNN that introduced important techniques such as ReLU activation, Dropout and GPU-based training. It provided an improvement over LeNet-5 in this experiment.

### 3. VGG16

VGG16 uses repeated 3 × 3 convolution filters and a deeper network structure. In this experiment, VGG16 was also used for transfer learning with pretrained ImageNet weights.

### 4. GoogleNet

GoogleNet uses Inception modules, where different convolution operations are performed in parallel. This allows the model to capture features at different scales while keeping the parameter count relatively low.

### 5. ResNet50

ResNet50 uses residual connections to make the training of deeper networks easier. It achieved the highest test accuracy among the models tested in this experiment.

---

## Transfer Learning with VGG16

VGG16 was initialized using pretrained **ImageNet weights**.

The original classifier was replaced with a new classification head suitable for the 10 CIFAR-10 classes.

Two stages were performed:

1. **Frozen Base**
   - The pretrained convolutional layers were kept frozen.
   - Only the newly added classifier was trained.

2. **Fine Tuning**
   - The last convolutional block was unfrozen.
   - The selected pretrained layers were allowed to adapt to CIFAR-10 images.

### VGG16 Results

| Configuration | Best Validation Accuracy |
|---------------|--------------------------|
| Frozen Base | 65.12% |
| Fine Tuned | 77.40% |

Fine tuning improved the best validation accuracy by **12.28 percentage points**.

---

## Hyperparameter Study

Different training settings were also compared, including:

- Learning rate
- Batch size
- Number of epochs
- Optimizer
- Dense-layer size
- Frozen vs partially frozen layers

The partial-freezing configuration gave the highest test accuracy among the tested hyperparameter configurations:

**70.32%**

---

## Adam vs SGD

The effect of the optimizer was also studied using the same baseline settings.

| Optimizer | Test Accuracy |
|-----------|---------------|
| Adam | 60.06% |
| SGD | 56.45% |

For the tested configuration, Adam performed better than SGD.

---

## Final Results

The final performance of the CNN architectures is summarized below.

| Model | Parameters | Test Accuracy | Training Time |
|-------|------------|---------------|---------------|
| LeNet-5 | 136,886 | 62.04% | 60.56 s |
| AlexNet | 35,855,178 | 66.78% | 269.93 s |
| GoogleNet | 223,150 | 73.37% | 133.26 s |
| VGG16 | 14,781,642 | 76.90% | 225.25 s |
| ResNet50 | 21,299,146 | **79.77%** | 1502.65 s |

ResNet50 achieved the highest test accuracy, while LeNet-5 required the least training time.

---

## Classification Metrics

| Model | Accuracy | Precision | Recall | F1-score |
|-------|----------|-----------|--------|----------|
| LeNet-5 | 62.04% | 62.11% | 62.04% | 61.50% |
| AlexNet | 66.78% | 68.09% | 66.78% | 66.45% |
| GoogleNet | 73.37% | 73.55% | 73.37% | 73.07% |
| VGG16 | 76.90% | 77.95% | 76.90% | 77.13% |
| ResNet50 | **79.77%** | **80.49%** | **79.77%** | **79.74%** |

---

## Observations

Some important observations from the experiment were:

- ResNet50 achieved the highest test accuracy of **79.77%**.
- LeNet-5 was the fastest model to train, taking only **60.56 seconds**.
- GoogleNet achieved **73.37%** accuracy with only **223,150 parameters**, showing that a large parameter count is not always necessary for good performance.
- VGG16 improved considerably after fine tuning.
- Fine tuning increased the best VGG16 validation accuracy from **65.12% to 77.40%**.
- Adam performed better than SGD for the tested configuration.
- The deeper models generally provided better classification performance, but they also required more computational time.

---

## Plots and Evaluation

The experiment includes:

- Sample CIFAR-10 images
- Training accuracy
- Validation accuracy
- Training loss
- Validation loss
- Confusion matrix
- Classification reports
- Model comparison plots
- Parameter comparison
- Training-time comparison

Misclassified images were treated as an optional output as specified in the laboratory manual.

---

## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Scikit-learn
- CIFAR-10 Dataset
- Google Colab

---

## Conclusion

This experiment provided a practical comparison of different CNN architectures on the CIFAR-10 dataset. ResNet50 achieved the best classification performance with a test accuracy of **79.77%**, while LeNet-5 was the fastest model to train. The VGG16 transfer learning experiment also showed that fine tuning pretrained features can significantly improve performance. Overall, the results showed that model selection involves a trade-off between accuracy, model size, training time and computational cost.
