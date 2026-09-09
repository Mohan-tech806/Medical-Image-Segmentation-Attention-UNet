# Medical Image Segmentation using Attention-Enhanced U-Net

This project focuses on automatic skin-lesion segmentation using the ISIC 2018 Task 1 dataset.

Three U-Net based models were implemented and compared:

1. Baseline U-Net
2. U-Net + CBAM
3. U-Net + SimAM

## Dataset

- Dataset: ISIC 2018 Task 1
- Total image-mask pairs: 2,594
- Image size: 256 × 256
- Train: 80%
- Validation: 10%
- Test: 10%

## Methodology

The project first implements a standard U-Net as a baseline model. Two attention-based variants are then developed to improve feature representation and lesion localization.

### Baseline U-Net

A standard encoder-decoder U-Net architecture with skip connections was implemented.

- Loss: Binary Cross-Entropy + Dice Loss
- Optimizer: Adam
- Learning Rate: 1e-4
- Batch Size: 16
- Maximum Epochs: 50

**Results:**
- Dice: 0.8625
- IoU: 0.7596
- Loss: 0.3254

### U-Net + CBAM

CBAM (Convolutional Block Attention Module) was added to improve channel and spatial feature attention.

**Results:**
- Dice: 0.8712
- IoU: 0.7744
- Loss: 0.3197

### U-Net + SimAM

SimAM (Simple Attention Module) was incorporated at the bottleneck of U-Net. SimAM is a parameter-free attention mechanism.

**Results:**
- Dice: 0.8778
- IoU: 0.7830
- Loss: 0.2906

## Results Comparison

| Model | Dice | IoU | Loss |
|---|---:|---:|---:|
| U-Net | 0.8625 | 0.7596 | 0.3254 |
| U-Net + CBAM | 0.8712 | 0.7744 | 0.3197 |
| U-Net + SimAM | 0.8778 | 0.7830 | 0.2906 |

SimAM achieved the best performance among the three models.

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