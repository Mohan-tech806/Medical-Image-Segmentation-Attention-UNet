# Medical Image Segmentation using Attention-Enhanced U-Net

Automatic skin-lesion segmentation on the ISIC 2018 Task 1 dataset, comparing a baseline U-Net against two attention-enhanced variants (CBAM and SimAM).

## Overview

Three U-Net based models were implemented and compared:

1. **Baseline U-Net**
2. **U-Net + CBAM** (Convolutional Block Attention Module)
3. **U-Net + SimAM** (Simple Attention Module)

The goal is to evaluate whether attention mechanisms improve lesion localization and segmentation accuracy over a standard encoder-decoder U-Net.

## Dataset

| Property | Value |
|---|---|
| Dataset | ISIC 2018 Task 1 |
| Total image-mask pairs | 2,594 |
| Image size | 256 × 256 |
| Train split | 80% |
| Validation split | 10% |
| Test split | 10% |

## Methodology

The project first implements a standard U-Net as a baseline model. Two attention-based variants are then developed to improve feature representation and lesion localization.

### Baseline U-Net

A standard encoder-decoder U-Net architecture with skip connections.

- **Loss:** Binary Cross-Entropy + Dice Loss
- **Optimizer:** Adam
- **Learning Rate:** 1e-4
- **Batch Size:** 16
- **Maximum Epochs:** 50

**Test Results**

| Metric | Score |
|---|---|
| Dice | 0.8589 |
| IoU | 0.7542 |
| Loss | 0.3208 |

### U-Net + CBAM

CBAM was added to improve channel and spatial feature attention.

**Test Results**

| Metric | Score |
|---|---|
| Dice | 0.8712 |
| IoU | 0.7744 |
| Loss | 0.3197 |

### U-Net + SimAM

SimAM, a parameter-free attention mechanism, was incorporated at the bottleneck of U-Net.

**Test Results**

| Metric | Score |
|---|---|
| Dice | 0.8778 |
| IoU | 0.7830 |
| Loss | 0.2906 |

## Results Comparison

| Model | Dice | IoU | Loss |
|---|---:|---:|---:|
| U-Net | 0.8589 | 0.7542 | 0.3208 |
| U-Net + CBAM | 0.8712 | 0.7744 | 0.3197 |
| **U-Net + SimAM** | **0.8778** | **0.7830** | **0.2906** |

**U-Net + SimAM achieved the best performance among the three models.**

## Evaluation

The models were evaluated using:

- Dice Coefficient
- Intersection over Union (IoU)
- Test Loss

The notebooks also include training curves and visual comparisons between the original image, ground-truth mask, and predicted segmentation mask.


## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

## Key Takeaway

Attention-enhanced U-Net models improved segmentation performance compared with the baseline U-Net, with U-Net + SimAM achieving the highest Dice and IoU scores.

