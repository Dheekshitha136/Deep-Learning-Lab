# Effect of Attention Type and Attention Position in a Pretrained ResNet50

## Overview

This project investigates the effect of different attention mechanisms and their placement within an ImageNet-pretrained ResNet50 for image classification. Experiments use the TensorFlow Flowers dataset, which contains five classes: Daisy, Dandelion, Roses, Sunflowers, and Tulips.

The study compares baseline ResNet50 performance with attention-based configurations and evaluates classification accuracy, model complexity, inference time, and visual explanations of model behavior.

## Objectives

- Establish a baseline using pretrained ResNet50.
- Compare channel, spatial, channel–spatial, and self-attention.
- Investigate attention placement at stages P1–P4.
- Analyze multi-stage attention, attention ordering, and spatial kernel size.
- Explore additional attention mechanisms such as SE, ECA, CBAM, and Coordinate Attention where implemented.
- Evaluate accuracy, macro precision, macro recall, macro F1-score, parameter counts, and inference time.
- Visualize learning curves, confusion matrices, attention maps, feature maps, overlays, and Grad-CAM.
- Address the 35 conceptual questions associated with the laboratory tasks.

## Dataset and Environment

- **Dataset:** TensorFlow Flowers
- **Number of classes:** 5
- **Classes:** Daisy, Dandelion, Roses, Sunflowers, Tulips
- **Data split:** 70% training, 15% validation, and 15% testing
- **Execution environment:** Google Colab
- **Backbone:** ImageNet-pretrained ResNet50

## Experiments

The experiments include:

1. Baseline ResNet50 classification.
2. Channel attention and spatial attention at selected stages.
3. Combined channel–spatial attention.
4. Self-attention.
5. Attention placement comparisons across P1–P4.
6. Multi-stage attention configurations.
7. Channel–spatial attention ordering comparisons.
8. Spatial attention kernel-size comparisons.
9. Additional attention mechanisms, including SE, ECA, CBAM, and Coordinate Attention where implemented.

## Evaluation Metrics

The models are evaluated using:

- Accuracy
- Macro precision
- Macro recall
- Macro F1-score
- Total model parameters
- Trainable parameters
- Average inference time per image

Additional analysis includes training and validation curves, confusion matrices, class-wise performance, attention visualizations, and Grad-CAM.

## Recorded Results

The following table summarizes the recorded main mechanism-comparison results.

| Model | Accuracy | Macro Precision | Macro Recall | Macro F1 | Parameters | Inference Time (ms/image) |
|---|---:|---:|---:|---:|---:|---:|
| Baseline ResNet50 | 93.47% | 93.50% | 93.32% | 93.39% | 23,597,957 | 7.5523 |
| Channel Attention (P3) | 94.01% | 94.09% | 93.76% | 93.89% | 23,730,117 | 7.8073 |
| Spatial Attention (P3) | 92.92% | 92.75% | 92.93% | 92.83% | 23,598,056 | 7.6747 |
| Channel–Spatial Attention (P3) | 92.01% | 91.96% | 92.06% | 91.94% | 23,730,216 | 7.8358 |
| Self-Attention (P3) | 93.47% | 93.60% | 93.31% | 93.43% | 24,909,958 | 7.9642 |
| SE | 93.10% | 93.00% | 93.12% | 93.02% | 23,730,117 | 7.8236 |
| ECA | 92.01% | 91.91% | 92.26% | 92.01% | 23,597,960 | 7.8548 |
| CBAM | 92.38% | 92.46% | 92.20% | 92.28% | 23,730,216 | 8.1261 |

### Key Observation

Channel attention at P3 achieved the highest recorded accuracy of **94.01%** and macro F1-score of **93.89%**, compared with baseline accuracy of 93.47% and macro F1-score of 93.39%.

The combined channel–spatial attention configuration at P3 did not outperform the baseline in this experiment. These results show that the effectiveness of attention depends on the mechanism and its placement rather than simply on adding more attention components.

Inference-time values may vary with hardware and execution conditions. Timing measurements from separate experiments should be checked for consistency before being combined.

## Visualizations and Analysis

The project includes or examines the following outputs, depending on the experiment:

- Training and validation accuracy/loss curves
- Accuracy and macro F1-score comparisons
- Accuracy versus parameter count
- Macro F1-score versus inference time
- Confusion matrices
- Class-wise performance comparisons
- Attention maps and feature maps
- Attention overlays
- Grad-CAM visualizations
- Correct and incorrect prediction examples
- Attention-position, ordering, kernel-size, and multi-stage comparisons

## Running the Experiments

The experiments are designed to run in Google Colab.

1. Open the project notebook in Google Colab.
2. Ensure the required Python packages and TensorFlow/Keras environment are available.
3. Load the TensorFlow Flowers dataset.
4. Apply the documented dataset split and preprocessing.
5. Train and evaluate the baseline ResNet50 model.
6. Run the attention-based configurations using the same evaluation protocol.
7. Generate the evaluation metrics and visualizations.
8. Compare the results and document the observations.

Record the actual optimizer, batch size, epoch count, learning-rate schedule, augmentation settings, random seed, and fine-tuning strategy from the executed experiments.

## Reproducibility

For fair comparison, keep the following consistent wherever applicable:

- Dataset split and random seed
- Input dimensions and preprocessing
- Data augmentation
- Backbone initialization and classification head
- Optimizer and learning-rate schedule
- Batch size and number of epochs
- Fine-tuning strategy
- Evaluation metrics and inference-time measurement procedure

Record each attention mechanism and its insertion position. Only report numerical values supported by the actual experimental results.

## Limitations

- Performance depends on the dataset, training configuration, and execution environment.
- Results on five flower classes may not generalize to unrelated image-classification tasks.
- Small performance differences may be affected by random initialization and data ordering.
- Inference time can vary with hardware and measurement conditions.
- Attention maps and Grad-CAM help visualize model behavior but do not establish causal explanations.

## Academic Context

This project was completed as part of the **CS3807 Deep Learning Laboratory**. It studies the effect of attention mechanism type and placement in a pretrained ResNet50 using quantitative performance evaluation and visual analysis.
