# Experiment 7 — End-to-End Study of Autoencoders

This repository contains the implementation, experiments, results, visualizations, and report for **CS3807 – Deep Learning Laboratory, Experiment 7**.

The experiment studies different types of autoencoders using the **MNIST handwritten digit dataset**, focusing on image reconstruction, denoising, latent-space representation, and image generation.

## Objectives

- Understand the encoder–latent–decoder architecture of an autoencoder.
- Implement a Fully Connected Autoencoder (FC-AE).
- Implement a Convolutional Autoencoder (CAE).
- Implement a Denoising Convolutional Autoencoder.
- Implement a Variational Autoencoder (VAE).
- Evaluate reconstruction using MSE, MAE, and SSIM.
- Study the effect of latent dimension on reconstruction.
- Visualize the VAE latent space.
- Generate new images using the VAE.
- Perform latent-space interpolation.
- Analyze reconstruction errors and high-error samples.

## Models Implemented

### 1. Fully Connected Autoencoder

Architecture:

`784 → 128 → 32 → 16 → 32 → 128 → 784`

- Latent dimension: 16
- Hidden activation: ReLU
- Output activation: Sigmoid
- Optimizer: Adam
- Learning rate: 0.001
- Batch size: 128
- Epochs: 20
- Loss: Binary Cross-Entropy

### 2. Convolutional Autoencoder

The convolutional autoencoder preserves the spatial structure of the input image.


Input: 28 × 28 × 1
        ↓
Conv2D(32)
        ↓
MaxPooling2D
        ↓
Conv2D(64)
        ↓
MaxPooling2D
        ↓
Conv2D(64)
        ↓
UpSampling2D
        ↓
Conv2D(32)
        ↓
UpSampling2D
        ↓
Conv2D(1)
        ↓
Output: 28 × 28 × 1

3. Denoising Autoencoder

The denoising autoencoder receives a corrupted image and learns to reconstruct the original clean image.

Clean Image
     ↓
  Add Noise
     ↓
Noisy Image
     ↓
   Encoder
     ↓
Latent Representation
     ↓
   Decoder
     ↓
Denoised Image

The experiment considers:

Gaussian noise
Salt-and-pepper noise
4. Variational Autoencoder

The VAE learns a probability distribution over the latent representation.

For the main experiment:

Latent dimension: 2
Prior distribution: N(0, I)
Reparameterization:
z = μ + σ ⊙ ε
ε ~ N(0, I)

The VAE objective is:

VAE Loss = Reconstruction Loss + KL Divergence
Dataset

Dataset: MNIST Handwritten Digit Dataset

Image size: 28 × 28 × 1
Grayscale images
Pixel values normalized to [0, 1]
Classes: digits 0–9

A controlled subset of MNIST was used for the experiments.

Main Results
Model	MSE	MAE	SSIM	Parameters	Time (s)
Fully Connected AE	0.022480	0.059559	0.730615	211040	12.9490
Convolutional AE	0.002697	0.015370	0.973007	74497	19.8459
Denoising CAE	0.003673	0.018712	0.954060	74497	35.9426
VAE (z = 2)	0.044133	0.103115	0.491307	485957	30.0672
Denoising Results
Gaussian Noise
σ	MSE	MAE	SSIM
0.1	0.002608	0.015477	0.968226
0.2	0.003673	0.018712	0.954060
0.3	0.005617	0.023899	0.926540
Salt-and-Pepper Noise
Noise Level	MSE	MAE	SSIM
0.05	0.002882	0.015879	0.969445
0.10	0.003533	0.017576	0.961389
0.20	0.005555	0.022419	0.936122

Increasing the corruption level increased MSE and MAE while decreasing SSIM for both noise types.

Latent Dimension Study

The Fully Connected Autoencoder was evaluated with different latent dimensions.

Latent Dimension	MSE	SSIM
2	0.057100	0.303824
8	0.033302	0.623377
16	0.024675	0.705872
32	0.021498	0.743559

The results show that increasing the latent dimension reduced reconstruction error in this experiment because more information could be retained in the latent representation.

Additional Experiments

The repository also contains:

CAE latent-dimension study
Gaussian noise vs. salt-and-pepper noise
SSIM comparison at two noise levels
UpSampling2D vs. Conv2DTranspose decoder
VAE latent dimension 2 vs. 8
Effect of β on KL-loss contribution
100 randomly generated VAE samples
Latent-region interpolation between digit 1 and digit 7
Visualizations

The experiment generates visualizations for:

Original vs. reconstructed images
FC-AE training and validation loss
FC-AE vs. CAE reconstruction
Clean, noisy and denoised images
Gaussian noise reconstruction metrics
VAE latent-space visualization
VAE-generated samples
VAE latent-space interpolation
VAE reconstruction loss
Reconstruction-error distribution
Top 5 high-error images
Latent dimension vs. MSE
100 VAE-generated samples
Latent-region interpolation
Repository Structure
Experiment-7-Autoencoders/
│
├── Experiment_7_Autoencoders_MASTER_ALL_TASKS.ipynb
├── README.md
│
├── plots_eps_600dpi/
│   ├── 01_fc_original_reconstruction.eps
│   ├── 02_fc_training_validation_loss.eps
│   ├── 03_fc_vs_cae.eps
│   ├── 04_clean_noisy_denoised.eps
│   ├── 05_gaussian_mse.eps
│   ├── 05_gaussian_mae.eps
│   ├── 05_gaussian_ssim.eps
│   ├── 06_vae_latent_space.eps
│   ├── 07_vae_25_generated.eps
│   ├── 08_vae_latent_interpolation.eps
│   ├── 09_vae_reconstruction_loss.eps
│   ├── 10_reconstruction_error_distribution.eps
│   ├── 11_top5_high_error.eps
│   ├── 12_latent_dimension_vs_mse.eps
│   ├── 16_vae_100_generated.eps
│   └── 17_latent_region_interpolation.eps
│
├── tables/
│   ├── additional_01_cae_latent_dimensions.csv
│   ├── additional_02_noise_type_comparison.csv
│   ├── additional_03_two_noise_levels_ssim.csv
│   ├── additional_04_decoder_comparison.csv
│   ├── additional_05_vae_latent_2_vs_8.csv
│   └── additional_06_kl_beta_study.csv
│
└── report/
    └── Experiment_7.tex
Requirements

The experiments were implemented using Python and TensorFlow/Keras.

Install the required packages:

pip install tensorflow numpy pandas matplotlib scikit-learn scikit-image
How to Run

Clone the repository:

git clone <your-repository-url>
cd Experiment-7-Autoencoders

Open:

Experiment_7_Autoencoders_MASTER_ALL_TASKS.ipynb

The notebook can be executed using Google Colab or Jupyter Notebook/JupyterLab.

Running the notebook performs the model training, evaluation, metric calculation, visualization generation, and result-table generation.

References
Ian Goodfellow, Yoshua Bengio and Aaron Courville, Deep Learning, MIT Press, 2016.
Diederik P. Kingma and Max Welling, Auto-Encoding Variational Bayes, ICLR, 2014.
Pascal Vincent et al., Stacked Denoising Autoencoders: Learning Useful Representations in a Deep Network with a Local Denoising Criterion, Journal of Machine Learning Research, 2010.
Yann LeCun, Corinna Cortes and Christopher J. C. Burges, MNIST Handwritten Digit Database.
TensorFlow Documentation.
Keras Documentation.
scikit-image Documentation.
