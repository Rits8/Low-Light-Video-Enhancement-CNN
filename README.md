# CNN-Based Real-Time Enhancement for Low-Light Video

A Deep Learning and Computer Vision project focused on enhancing low-light CCTV footage using a Convolutional Neural Network (CNN) trained to remove multiple real-world noise types.

This project addresses one of the biggest practical problems in surveillance systems — poor visibility and heavy noise in low-light video recordings.

# Problem Statement

CCTV cameras often fail to capture usable footage in low-light environments. The recorded videos suffer from:

Gaussian Noise (random pixel variations)

Speckle Noise (granular interference)

Poisson Noise (photon limitation in darkness)

Low brightness and poor contrast

Most traditional enhancement techniques and many research models handle only a single type of noise. However, real CCTV footage contains a combination of these noises, making enhancement challenging.

# Proposed Solution

We designed a CNN-based frame enhancement pipeline that:

Extracts frames from low-light video using OpenCV

Adds synthetic Gaussian, Speckle, and Poisson noise to simulate real CCTV conditions

Trains a CNN model using TensorFlow/Keras to learn noise removal and brightness enhancement

Enhances each frame individually

Reconstructs the enhanced frames back into a clean video stream

# Methodology
## Step 1 — Frame Extraction

The input video is decomposed into frames using OpenCV for individual processing.

## Step 2 — Noise Simulation

To mimic real-world CCTV scenarios, frames are synthetically darkened and injected with:

Gaussian noise

Speckle noise

Poisson noise

## Step 3 — CNN Model Training

A lightweight CNN architecture with skip connections and residual enhancement layers is trained using noisy-clean image pairs.

## Step 4 — Frame Enhancement

Each noisy frame is passed through the trained CNN model to improve:

Brightness

Contrast

Detail visibility

Noise reduction

## Step 5 — Video Reconstruction

Enhanced frames are reassembled into a video using OpenCV’s VideoWriter.

# Tech Stack
Tool	                        Purpose
Python	                 Core programming
OpenCV	                 Frame extraction & video reconstruction
TensorFlow / Keras	     CNN model development
NumPy	                   Numerical operations
Matplotlib	             Visualization
scikit-image	           PSNR & SSIM evaluation
Google Colab	           Training environment

# Performance Metrics

The model is evaluated using standard image quality metrics:

PSNR (Peak Signal-to-Noise Ratio) — Measures noise reduction quality

SSIM (Structural Similarity Index) — Measures structural similarity with ground truth

MSE (Mean Squared Error) — Measures pixel-level difference

The model performs strongly for individual and combined noise scenarios in low-light conditions.

# How to Run the Project

Open the notebook inside the notebook/ folder in Google Colab.

Upload the dataset or connect to Google Drive.

Run all cells to:

Preprocess images

Train the CNN model

Test on images

Generate enhanced video

# Future Improvements

Improve performance on combined noise scenarios

Add temporal consistency across frames to reduce flicker

Deploy on Jetson Nano / Raspberry Pi for real-time CCTV use

Integrate with face recognition for smart surveillance
