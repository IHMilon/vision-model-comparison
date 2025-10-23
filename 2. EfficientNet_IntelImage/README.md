
# EfficientNet on Intel Image Dataset

## Overview
This project implements a **custom EfficientNet-style CNN** from scratch in **PyTorch** for the **Intel Image Classification dataset**.  
The model is designed to balance **accuracy, efficiency, and computational cost**, making it well-suited for experimentation and deployment on limited hardware.

## References
- **Paper:** [EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks](https://arxiv.org/abs/1905.11946)  
- **Dataset:** [Intel Image Classification Dataset](https://www.kaggle.com/datasets/puneet6060/intel-image-classification)

## Dataset
- **Total Images:** 25k RGB images (Resized to 128×128 resolution)  
- **Classes:** 6 scene categories  *buildings, forest, glacier, mountain, sea, street*  
- **Split:** 14k training / 3k validation / 7k testing samples (Not used here)

## Model Architecture
- **Structure:** Custom **EfficientNet backbone** built from MBConv blocks with depthwise separable convolutions and squeeze-and-excitation (SE) layers.  
- **Expansion Factor:** Reduced from `6` → `5` to minimize overfitting and computation.  
- **Parameters:** 3.5M (reduced from 7M)  
- **MACs:** 269M (reduced from 450M)  
- **Input Size:** 128×128 

## Results
| Metric | Train | Test |
|:--------|:-------:|:------:|
| **Accuracy** | 90% | 86.8% |

- **Training Time:** 58 minutes (with mixed precision)
- **Inference Latency:** **162.37 ms per batch (128 images)**  
- **Throughput:** **1,576 images/second**
- **Visuals:** Accuracy/Loss curves, confusion matrix available in the `results/` folder  

## Key Insights
- Reducing the **expansion factor** improved generalization and reduced overfitting without sacrificing performance.  
- **Efficient scaling** across depth and width preserved accuracy while cutting computational cost nearly in half.  
- The model demonstrates the **EfficientNet philosophy** — achieving higher accuracy with fewer parameters and operations.  

## Analysis
- The use of **depthwise separable convolutions** and **SE layers** greatly enhances efficiency and feature selectivity.  
- **Balanced architecture scaling** ensures better feature learning for mixed-scene images such as those in the Intel dataset.
