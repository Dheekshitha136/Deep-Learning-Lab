# CS3807 – Deep Learning Laboratory
## Experiment 6: End-to-End Study of RNN, LSTM and GRU for Sequence Learning and Video Understanding

### Overview
This experiment implements and compares Vanilla RNN, LSTM and GRU models for sequence classification using the UCI Human Activity Recognition (HAR) dataset. It also covers BPTT, sequence-length analysis, video understanding using CNN features with LSTM/GRU, and Seq2Seq learning.

### Experiments Covered
- UCI HAR preprocessing and temporal visualization
- Vanilla RNN implementation and evaluation
- Numerical RNN hidden-state calculation
- Backpropagation Through Time (BPTT)
- LSTM implementation and evaluation
- GRU implementation and evaluation
- RNN vs LSTM vs GRU comparison
- Sequence length analysis using 32, 64 and 128 time steps
- Training-time and parameter-count comparison
- Video classification using MobileNetV2 + LSTM/GRU
- Seq2Seq encoder-decoder sequence reversal
- Seq2Seq task with different input/output lengths
- Seven additional exercises
- Confusion-matrix and training/validation-curve analysis

### Main HAR Results

| Model | Accuracy | Macro F1 | Parameters | Training Time |
|---|---:|---:|---:|---:|
| Vanilla RNN | 65.22% | 63.19% | 1,974 | 28.97 s |
| LSTM | 87.00% | 86.78% | 6,006 | 20.70 s |
| GRU | 89.01% | 88.96% | 4,758 | 19.89 s |

### Sequence Length Results

| Sequence Length | RNN F1 | LSTM F1 | GRU F1 |
|---|---:|---:|---:|
| 32 | 68.22% | 84.83% | 84.69% |
| 64 | 68.78% | 85.46% | 89.08% |
| 128 | 63.19% | 86.78% | 88.96% |

### Video Results

The video pipeline uses pretrained MobileNetV2 to extract 1280-dimensional features from 10 sampled frames, followed by an LSTM or GRU for temporal processing.

| Model | Accuracy | Macro F1 | Parameters |
|---|---:|---:|---:|
| CNN–LSTM | 96.43% | 96.19% | 168,643 |
| CNN–GRU | 89.29% | 88.85% | 126,723 |

The video experiment uses three classes: Archery, Basketball and BaseballPitch, with 28 test videos.

### Seq2Seq Results

- Original 4-to-4 reversal task: **100.00% token accuracy and 100.00% exact sequence accuracy**
- Modified 4-to-5 task: **85.52% token accuracy and 30.53% exact sequence accuracy**
- The modified task demonstrates the difference between token-level and complete-sequence evaluation.

### Dataset
- **UCI Human Activity Recognition Using Smartphones**
- 6 activity classes
- 128 time steps per sequence
- 9 sensor channels
- 1800 balanced samples used for the main experiment
- 70:15:15 train/validation/internal-test split
- Official UCI test set: 2947 samples

### Technologies Used
- Python
- TensorFlow / Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- MobileNetV2
- UCI HAR Dataset

### Key Outcome
The experiment demonstrates how recurrent architectures can process different types of sequential information, including sensor signals, CNN-extracted video features and symbolic sequences. The measured performance varies with the recurrent architecture, sequence length and task definition.
