# Deep Learning Lab – Experiment 3
## Convolutional Neural Networks (CNN) using CIFAR-10

### Overview

This experiment focuses on understanding the basic working of Convolutional
Neural Networks (CNNs) through image classification using the CIFAR-10
dataset and TensorFlow/Keras.

The experiment covers convolution operations, kernel sizes, stride, padding,
feature-map visualization, pooling methods, CNN training and evaluation.
Different CNN configurations were also compared to understand their effect
on classification performance.

---

## Dataset

The experiment uses the **CIFAR-10 dataset**, which contains:

- 50,000 training images
- 10,000 testing images
- 10 classes
- Image size: `32 × 32 × 3`

The ten classes are:

1. Airplane
2. Automobile
3. Bird
4. Cat
5. Deer
6. Dog
7. Frog
8. Horse
9. Ship
10. Truck

Each class contains 5,000 training images, making the training dataset
balanced.

---

## Objectives

The main objective of this experiment is to understand the working principle
of CNNs by implementing:

- Convolution operations
- Different kernel sizes
- Stride and padding
- Feature-map visualization
- Max pooling and average pooling
- CNN image classification
- Model performance evaluation

---

## Tasks Performed

### Task 1 – CIFAR-10 Dataset

- Loaded the CIFAR-10 dataset.
- Displayed sample images from different classes.
- Checked the dataset dimensions.
- Plotted the class distribution.

### Task 2 – Effect of Kernel Size

Three convolution kernel sizes were compared:

- `3 × 3`
- `5 × 5`
- `7 × 7`

Using valid padding, the obtained feature-map sizes were:

| Kernel Size | Feature Map Size |
|-------------|------------------|
| 3 × 3 | 30 × 30 |
| 5 × 5 | 28 × 28 |
| 7 × 7 | 26 × 26 |

The number of filters was kept at 8 for this comparison.

---

### Task 3 – Effect of Stride and Padding

The effect of stride and padding on the output dimensions was studied.

| Configuration | Output Size |
|---------------|-------------|
| Stride = 1 | 30 × 30 |
| Stride = 2 | 15 × 15 |
| Same Padding | 32 × 32 |
| Valid Padding | 30 × 30 |

The experiment showed that increasing the stride reduces the spatial size of
the feature map, while same padding can retain the original spatial
dimensions.

---

### Task 4 – Feature Map Visualization

Feature maps obtained after the first convolution layer were visualized.

A total of **8 feature maps** were displayed. Different filters responded
to different parts of the same image, including edges, brighter regions and
other image patterns.

---

### Task 5 – Max Pooling vs Average Pooling

Max pooling and average pooling were compared using the same CNN structure.

Both methods produced an output size of:

`8 × 8 × 32`

The obtained results were:

| Pooling Method | Accuracy | Precision | Recall | F1-score |
|----------------|----------|-----------|--------|----------|
| Max Pooling | 68.80% | 69.00% | 68.80% | 68.59% |
| Average Pooling | 69.31% | 69.20% | 69.31% | 69.18% |

Average pooling performed slightly better than max pooling in this
experiment.

---

## CNN Architecture

The final CNN followed the architecture:

```text
Input
  ↓
Convolution
  ↓
ReLU
  ↓
Max Pooling
  ↓
Convolution
  ↓
ReLU
  ↓
Max Pooling
  ↓
Flatten
  ↓
Dense
  ↓
Softmax
